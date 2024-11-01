# What Makes Pulumi Different

## Evolution of Infrastructure Code
<v-clicks>

- HCL/YAML (Terraform)
  ```hcl
  resource "azurerm_container_app" "example" {
    name                = "example-app"
    resource_group_name = azurerm_resource_group.example.name
  }
  ```

- Real Programming Languages (Pulumi)
  ```csharp
  var app = new ContainerApp("example-app", new ContainerAppArgs
  {
      ResourceGroupName = resourceGroup.Name
  });
  ```

- Higher-Level Abstractions (Mews SDK)
  ```csharp
  var app = new WebApplication("example-app")
      .InResourceGroup(resourceGroup)
      .WithStandardConfiguration();
  ```

</v-clicks>

<!--
# Presenter Notes
- Show progression of abstraction levels
- Highlight benefits of each approach
- Connect to their programming experience
- Point out type safety advantages
-->

---

# Core Concepts

## Projects
<v-clicks>

- Unit of Infrastructure Code
- Configuration Management
- Dependencies Handling
- Team Collaboration
- Resource Organization

</v-clicks>

## Stacks (Environments)
<v-clicks>

- Development
- Staging
- Production
- Independent State
- Environment-Specific Settings

</v-clicks>

<!--
# Presenter Notes
- Connect to software project organization
- Explain environment separation
- Highlight configuration management
- Show how it scales with team size
-->

---

# Core Concepts (continued)

## Resources
<v-clicks>

- Cloud Components
- Dependency Management
- Resource Graph
- State Tracking
- Lifecycle Management

</v-clicks>

## State & Backend
<v-clicks>

- Resource State Tracking
- Change Management
- Team Collaboration
- Version History
- Rollback Capabilities

</v-clicks>

<!--
# Presenter Notes
- Emphasize resource relationships
- Explain state importance
- Connect to previous IaC principles
- Prepare for demo section
-->

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
- Connect to their C# knowledge
- Show IDE benefits later in demo
- Highlight productivity gains
- Compare to YAML/HCL limitations
-->

---

# Pulumi Architecture

## Components
<v-clicks>

- Language Host
  - Code Execution
  - Resource Registration
  - Program Runtime

- Deployment Engine
  - State Comparison
  - Change Orchestration
  - Resource Management

- Resource Providers
  - Cloud API Interaction
  - Resource Operations
  - State Management

</v-clicks>

<!--
# Presenter Notes
- Explain each component's role
- Connect to CS concepts
- Prepare for hands-on demo
- Link to their systems knowledge
-->

---

# Working with State

## State Management
<v-clicks>

- Resource Tracking
- Change Detection
- Dependency Resolution
- Consistent Deployments
- Team Synchronization

</v-clicks>

## State Backends
<v-clicks>

- Pulumi Service (Cloud)
- Self-Hosted Options
- Local State
- State Protection
- Collaboration Features

</v-clicks>

<!--
# Presenter Notes
- Explain state importance
- Show state file later in demo
- Discuss backend choices
- Connect to enterprise needs
-->