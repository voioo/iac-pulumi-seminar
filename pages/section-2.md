# The Traditional Way

## Manual Infrastructure Management
<v-clicks>

- Azure Portal click operations
- Individual resource creation
- Manual configuration steps
- Point-and-click changes
- No version control
- Limited documentation

## Common Issues
- Hard to replicate
- No history tracking
- Error-prone
- Team coordination challenges
- Tribal knowledge
- Configuration drift

</v-clicks>

<!--
# Presenter Notes
- Will demo portal briefly
- Ask: "How would you document these steps?"
- Point out all the small decisions made
- Highlight documentation challenges
-->

---

# Core IaC Principles

## 1. Infrastructure as Software
<v-clicks>

- Version control
- Code review process
- Testing capabilities
- Clear change history
- Collaborative development

</v-clicks>

## 2. Declarative Definitions
<v-clicks>

- Desired state specification
- System handles implementation
- Idempotent operations
- Predictable results
- Infrastructure as data

</v-clicks>

<!--
# Presenter Notes
- Connect to software development principles
- Emphasize shift in thinking
- Link to CS concepts they know
- Ask about benefits they see
-->

---

# Core IaC Principles (continued)

## 3. Automation First
<v-clicks>

- Repeatable processes
- Consistent results
- Reduced human error
- Scalable operations
- Audit capabilities

</v-clicks>

## 4. Immutable Infrastructure
<v-clicks>

- No manual changes
- Replace instead of modify
- Predictable states
- Version tracking
- Rollback capability

</v-clicks>

<!--
# Presenter Notes
- Highlight advantages of automation
- Connect to previous pets vs cattle concept
- Ask about their automation experience
- Draw parallels to software versioning
-->

---

# IaC Tools Landscape

## Configuration Management
<v-clicks>

- Ansible
- Chef
- Puppet
- Focus: Software and configs

</v-clicks>

## Infrastructure Provisioning
<v-clicks>

- Terraform
- Pulumi
- Focus: Resource creation

</v-clicks>

## Platform Specific
<v-clicks>

- ARM Templates (Azure)
- CloudFormation (AWS)
- Deployment Manager (GCP)
- Focus: Single cloud provider

</v-clicks>

<!--
# Presenter Notes
- Explain tool categories
- Discuss complementary usage
- Share real-world examples
- Set up for Pulumi deep-dive
-->

---

# The Development Workflow

## Standard Process
<v-clicks>

1. Write infrastructure code locally
2. Preview changes (dry run)
3. Create Pull Request
4. Team review process
5. Automated validation
6. Apply changes
7. Verify deployment

</v-clicks>

## Key Benefits
<v-clicks>

- Collaborative development
- Quality assurance
- Change tracking
- Risk reduction
- Team knowledge sharing

</v-clicks>

<!--
# Presenter Notes
- Show example PR later in demo
- Connect to standard dev practices
- Highlight review benefits
- Discuss team dynamics
-->

---

# Benefits & Challenges

## Immediate Benefits
<v-clicks>

- Version Control & History
- Familiar Developer Experience
- Consistency & Repeatability
- Documentation as Code
- State Management
- Team Collaboration

</v-clicks>

## Key Challenges
<v-clicks>

- Initial Learning Curve
- Setup Complexity
- Team Adoption
- State Management Complexity
- Legacy Integration

</v-clicks>

<!--
# Presenter Notes
- Use Mews examples where relevant
- Connect to previous portal demo issues
- Discuss how challenges are addressed
- Lead into Pulumi introduction
-->