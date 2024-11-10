---
layout: section
class: text-center
---

# Demonstration of app environment

<div class="opacity-80 italic mb-4">
Using pulumi to manage cloud environment
</div>

---
hideInToc: true
---

# Basic Infrastructure Implementation

## What We'll Build
<v-clicks>

- Resource Group
- SQL Server and Database
- Container App Environment
- Container App

</v-clicks>

<!--
# Presenter Notes
- Have Azure Portal open
- VS Code ready with extensions
- Terminal with Azure CLI logged in
- Check Pulumi login status

## Demo Goals

- Show real infrastructure code
- Demonstrate resource dependencies
- Handle secrets properly
- Manage configuration
- Deploy to Azure
-->

---
hideInToc: true
---

# Starting the project

<v-clicks>

1. Configuration
   ```csharp
    var config = new Config();
    var adminUsername = config.Require("sqlAdminUsername");
    var adminPassword = config.RequireSecret("sqlAdminPassword");
   ```

2. Resource Group
   ```csharp
    var resourceGroup = AzureResourceGroup.Create($"mews-pulumi-example-{location.Abbreviation}-tmp", location);
   ```

2. SQL Server
   ```csharp
   var sqlServer = new Server("demo-sql", new ServerArgs
   {
       ResourceGroupName = resourceGroup.Name,
       AdministratorLogin = "adminUser"
   });
   ```

</v-clicks>

<!--
# Presenter Notes
- Type code as you go
- Explain each property
- Show autocompletion
- Highlight dependency tracking
-->

---
hideInToc: true
---

# Adding long lived resources
<v-clicks>

1. Container app environment
   ```csharp
    var containerAppEnvironment = AzureContainerAppEnvironment.Create(
        name: $"pulumi-example-cae--{location.Abbreviation}",
        location: location,
        resourceGroup: resourceGroup,
        logDestination: new AzureMonitorDestination()
    );
   ```

2. SQL Server
   ```csharp
    var sqlServer = AzureSqlServer.Create(
        name: $"pulumi-example-sqlserver-{location.Abbreviation}",
        resourceGroup: resourceGroup,
        location: location,
        adminLogin: adminUsername,
        adminPassword: adminPassword,
        protectFromDeletion: false
    );
   ```

</v-clicks>

---
hideInToc: true
---

# Adding the database

<v-clicks>

## SQL Database
   ```csharp
    var database = AzureSqlDatabase.Create(
        resourceName: $"pulumi-example-database-{location.Abbreviation}",
        databaseName: $"example-app-database",
        resourceGroup: resourceGroup,
        location: location,
        server: sqlServer,
        tier: new StandardDbS2(50),
        readScaleOut: DatabaseReadScale.Disabled,
        zoneRedundant: false,
        highAvailabilityReplicaCount: 0,
        BackupStorageRedundancy.Local
    );
   ```
</v-clicks>

---
hideInToc: true
---

# Adding the app

<v-clicks>

## Container app
  ```csharp
    var app = AzureContainerApp.Create(
        name: $"pulumi-example-app-{location.Abbreviation}",
        resourceGroup: resourceGroup,
        location: location,
        containerName: "test-app",
        containerAppEnvironment: containerAppEnvironment,
        fullImageName: $"",
        containerResources: AzureContainerApp.GetResources(0.5, 2),
        minReplicas: 1,
        maxReplicas: 2,
        environmentVariables: null,
        secrets: null,
        dependsOn: database
    );
  ```
</v-clicks>

<!--
# Presenter Notes
- Explain SKU options
- Show how preview works
- Point out dependency chain
- Discuss production considerations
-->

---
hideInToc: true
---

# Exploring the changes

<v-clicks>

1. Show Preview
   ```bash
   pulumi preview
   ```

2. Check Generated Plan
   - Resource creation order
   - Property settings
   - Dependencies

</v-clicks>

---
hideInToc: true
---

# Live Deployment

## Deployment Steps
<v-clicks>

1. Final Code Review
2. Preview Changes
3. Execute Deployment
4. Verify Resources
5. Check Access

</v-clicks>

<!--
# Presenter Notes
- Run deployment live
- Show Azure portal results
- Verify configurations
- Demonstrate access

## Verification Points
- Resource Creation
- Configuration Application
- Security Settings
- Connectivity
- Monitoring Status
-->

---
hideInToc: true
---

# Making Changes

## Example Modifications
<v-clicks>

1. Change the resource requests for the container app
2. Preview changes
3. Deploy Changes

</v-clicks>

## Key Observations
<v-clicks>

- Change Detection
- State Management
- Dependency Updates
- Resource Protection
- Rollback Options

</v-clicks>

<!--
# Presenter Notes
- Make live changes
- Show state updates
- Demonstrate protection
- Discuss rollback
-->

---
hideInToc: true
---

# Preview Limitations

## What Preview Shows
<v-clicks>

- Resource Changes
- Configuration Updates
- Dependencies
- Basic Validation

</v-clicks>

## What Preview Misses
<v-clicks>

- API-Specific Rules
- Some Validation Rules
- Runtime Conditions
- External Dependencies

</v-clicks>

<!--
# Presenter Notes
- Show preview examples
- Discuss limitations
- Share workaround strategies
- Mention common pitfalls
-->

---
hideInToc: true
---

# Team Workflow Demo

## Pull Request Process
<v-clicks>

1. Create Branch
2. Make Changes
3. Run Preview
4. Create PR
5. Review Changes
6. Merge & Deploy

</v-clicks>

## Review Points
<v-clicks>

- Code Quality
- Security Checks
- Cost Impact
- Best Practices
- Team Standards

</v-clicks>

<!--
# Presenter Notes
- Show real PR example
- Discuss review process
- Highlight automation
- Share team practices
-->

---
layout: two-cols-header
hideInToc: true
---

# Benefits & Challenges

Making the transition to Infrastructure as Code

::left::

# Benefits

<div class="space-y-4">
  <div v-click class="benefit">
    Version Control
  </div>
  
  <div v-click class="benefit">
    Familiar Dev Experience
  </div>
  
  <div v-click class="benefit">
    Repeatability
  </div>
  
  <div v-click class="benefit">
    Self-Documenting
  </div>
  
  <div v-click class="benefit">
    Team Collaboration
  </div>
</div>

::right::

# Challenges

<div class="space-y-4">
  <div v-click class="challenge">
    Learning Curve
  </div>
  
  <div v-click class="challenge">
    Initial Setup
  </div>
  
  <div v-click class="challenge">
    Team Adoption
  </div>
  
  <div v-click class="challenge">
    State Management
  </div>
  
  <div v-click class="challenge">
    Legacy Integration
  </div>
</div>

<style>
.benefit, .challenge {
  @apply p-2 rounded;
}
.benefit {
  @apply bg-green-500 bg-opacity-10;
}
.challenge {
  @apply bg-orange-500 bg-opacity-10;
}
</style>

<!--
# Speaker Notes

Start with benefits:
- Each one connects to their dev experience
- Give quick examples for each
- Point out long-term gains

Then challenges:
- Be honest about difficulties
- Not appripriate at every scale
- But show they're manageable
- Most are one-time costs
- Common to all new tech adoption

Key message:
"Benefits compound over time, challenges decrease"

Ask:
"Which benefit interests you most?"
"Which challenge concerns you?"
-->

---
hideInToc: true
---

# Language Benefits

## Using C# for Infrastructure
<v-clicks>

- Strong Type System
- IDE Support
- Refactoring Tools
- Testing Framework
- Dependency Management
- Package Ecosystem

</v-clicks>

## Real Development Features
<v-clicks>

- Classes and Inheritance
- Error Handling
- Code Organization
- Documentation Tools
- Code Sharing
- Team Collaboration

</v-clicks>

<!--
# Presenter Notes
- Show IDE benefits later in demo
- Highlight productivity gains
- Compare to YAML/HCL limitations
-->