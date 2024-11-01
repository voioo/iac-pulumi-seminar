# The Platform Challenge

## Common Scaling Problems
<v-clicks>

- Teams waiting for infrastructure
- Inconsistent environments
- Security review bottlenecks
- Knowledge silos
- Repeated work across teams

</v-clicks>

## Traditional Approach
<v-clicks>

- Central team handles everything
- Tickets for infrastructure requests
- Manual reviews and approvals
- Long wait times
- Limited team autonomy

</v-clicks>

<!--
# Presenter Notes
- Connect to audience's experiences
- Ask about similar challenges
- Show natural evolution of needs
- Lead into platform solution
-->

---

# Internal Developer Platform

## Key Components
<v-clicks>

- Self-service infrastructure
- Standard building blocks
- Security by default
- Team independence with guardrails
- Shared services and patterns

</v-clicks>

## Benefits
<v-clicks>

### For Product Teams
- Faster delivery
- More autonomy
- Less cognitive load
- Focus on business problems

### For Platform Teams
- Controlled standardization
- Better security oversight
- Efficient scaling
- Focus on platform features

</v-clicks>

<!--
# Presenter Notes
- Emphasize balanced responsibility
- Show how it helps both sides
- Connect to their development experience
- Share real examples
-->

---

# Mews Journey

## Monolith Phase
<v-clicks>

- Single .NET application
- SQL Server database
- Everything in one codebase
- Simple deployment model

</v-clicks>

## Growth & Scaling
<v-clicks>

- Multiple instances
- Request-based routing
- Growing development team
- Deployment coordination challenges
- Rollback problems affecting everyone

</v-clicks>

<!--
# Presenter Notes
- Share real challenges faced
- Connect to their studies
- Show evolution of thinking
- Highlight learning points
-->

---

# Service Multiplication

## Changes Needed
<v-clicks>

- Breaking apart the monolith
- "You build it, you run it" mindset
- Teams needing infrastructure autonomy
- Growing operational complexity

</v-clicks>

## Infrastructure Impact
<v-clicks>

### Before
- One deployment process
- Central management
- Limited flexibility

### After
- Multiple independent services
- Team-owned infrastructure
- Need for standardization
- Platform team support

</v-clicks>

<!--
# Presenter Notes
- Explain why change was needed
- Share transition challenges
- Show benefits realized
- Connect to their future work
-->

---

# Building Our Infrastructure SDK

## Evolution of Approach
<v-clicks>

1. Initial Full Abstraction
```csharp
// First try - hiding everything
var service = new MewsService("orders").Deploy();
```

2. Flexible Configuration
```csharp
// Second iteration - too many options
var service = new MewsService("orders", new ServiceConfig 
{
    Database = new DatabaseConfig { ... },
    Network = new NetworkConfig { ... }
});
```

3. Building Blocks
```csharp
// Current approach - balanced abstraction
var database = new SqlDatabase("demo")
    .WithBasicTier()
    .WithBackups();
```

</v-clicks>

<!--
# Presenter Notes
- Show evolution of thinking
- Share lessons learned
- Explain current benefits
- Discuss trade-offs
-->

---

# Key Principles

## Design Philosophy
<v-clicks>

- Make complexity manageable, not invisible
- Standardize common patterns
- Enable team autonomy within guardrails
- Balance abstraction and control
- Provide escape hatches

</v-clicks>

## Implementation Focus
<v-clicks>

- Clear defaults with overrides
- Standard naming conventions
- Security by default
- Cost controls built-in
- Team-focused workflows

</v-clicks>

<!--
# Presenter Notes
- Explain each principle
- Share real examples
- Show how principles evolved
- Connect to their design experience
-->

---

# Current Challenges

## Technical Challenges
<v-clicks>

- Finding right abstraction level
- Maintaining backwards compatibility
- Growing complexity of SDK
- Testing infrastructure code
- Managing dependencies

</v-clicks>

## Team Challenges
<v-clicks>

- Adoption and training
- Documentation needs
- Balance of control
- Supporting diverse needs
- Keeping up with cloud changes

</v-clicks>

<!--
# Presenter Notes
- Share real challenges
- Discuss solutions found
- Show ongoing work
- Ask for their thoughts
-->