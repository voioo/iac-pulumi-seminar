# Basic Infrastructure Implementation

## What We'll Build
<v-clicks>

- Resource Group
- SQL Server and Database
- Container App
- Environment Configuration
- Security Setup

</v-clicks>

## Demo Goals
<v-clicks>

- Show real infrastructure code
- Demonstrate resource dependencies
- Handle secrets properly
- Manage configuration
- Deploy to Azure

</v-clicks>

<!--
# Presenter Notes
- Have Azure Portal open
- VS Code ready with extensions
- Terminal with Azure CLI logged in
- Check Pulumi login status
-->

---

# Starting Simple

## Resource Creation
<v-clicks>

1. Resource Group
   ```csharp
   var resourceGroup = new ResourceGroup("demo-rg");
   ```

2. SQL Server
   ```csharp
   var sqlServer = new Server("demo-sql", new ServerArgs
   {
       ResourceGroupName = resourceGroup.Name,
       AdministratorLogin = "adminUser"
   });
   ```

3. Configuration Management
   ```csharp
   var config = new Config();
   var adminPassword = config.RequireSecret("sqlAdminPassword");
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

# Adding Database

## Implementation Steps
<v-clicks>

1. Create Database
   ```csharp
   var database = new Database("demo-db", new DatabaseArgs
   {
       ResourceGroupName = resourceGroup.Name,
       ServerName = sqlServer.Name,
       Sku = new SkuArgs { Name = "Basic" }
   });
   ```

2. Show Preview
   ```bash
   pulumi preview
   ```

3. Check Generated Plan
   - Resource creation order
   - Property settings
   - Dependencies

</v-clicks>

<!--
# Presenter Notes
- Explain SKU options
- Show how preview works
- Point out dependency chain
- Discuss production considerations
-->

---

# Container App Setup

## Key Components
<v-clicks>

1. Container Registry Access
2. Environment Variables
3. Database Connection
4. Security Configuration
5. Health Monitoring

</v-clicks>

## Implementation Focus
<v-clicks>

- Resource Dependencies
- Secret Management
- Configuration Handling
- Security Best Practices
- Monitoring Setup

</v-clicks>

<!--
# Presenter Notes
- Show each component addition
- Explain security choices
- Demonstrate configuration
- Point out best practices
-->

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

## Verification Points
<v-clicks>

- Resource Creation
- Configuration Application
- Security Settings
- Connectivity
- Monitoring Status

</v-clicks>

<!--
# Presenter Notes
- Run deployment live
- Show Azure portal results
- Verify configurations
- Demonstrate access
-->

---

# Making Changes

## Example Modifications
<v-clicks>

1. Update Configuration
2. Add Resources
3. Modify Settings
4. Handle Dependencies
5. Deploy Changes

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