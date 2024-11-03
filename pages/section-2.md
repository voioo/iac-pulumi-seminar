---
layout: section
class: text-center
---

# Infrastructure as Code Foundations

<div class="opacity-80 italic mb-4">
From manual clicks to infrastructure at scale
</div>

<!--
# Speaker Notes

Transition points:
- We've seen how we got here
- Now let's look at how we solve it
- Connect past problems to current solutions
- Setup for hands-on learning

Energy shift:
- Moving from history to practical
- From "why" to "how"
- Getting ready for action
-->

---
layout: center
---

# Two Ways to Create Infrastructure

<div class="flex justify-center gap-16">
  <div v-click class="flex flex-col items-center">
    <div class="text-4xl mb-4">👆</div>
    <div class="text-xl font-bold mb-4">Click. Click. Click...</div>
    <div class="text-6xl">
      🖥️
    </div>
  </div>

  <div v-click class="flex flex-col items-center">
    <div class="text-4xl mb-4">⌨️</div>
    <div class="text-xl font-bold mb-4">Code Once, Deploy Many</div>
    <div class="font-mono bg-gray-800 rounded p-4 text-sm">
      resource webApp {
        name = "myapp"
        ...
      }
    </div>
  </div>
</div>

<div v-click class="mt-12 text-center text-xl">
  Let's see what this means in practice...
</div>

<!--
# Speaker Notes

Demo plan:
1. "Let me show you the traditional way first..."
2. Open Azure Portal
3. Start creating a web app
4. Point out:
   - Many clicks needed
   - Many decisions to make
   - Easy to miss steps
   - Hard to document
   - Even harder to repeat exactly

Questions to ask:
- "How would you document all these steps?"
- "How would you share this with your team?"
- "What happens when you need 10 of these?"

Key message:
Manual processes don't scale with modern needs
-->

---
layout: center
---
# Issues with manual management

<v-clicks>

- Scaling
- Hard to replicate
- No history tracking
- Error-prone
- Team coordination challenges
- Tribal knowledge
- Configuration drift

</v-clicks>
---
layout: two-cols-header
---

# Core IaC Principles

Infrastructure managed with the same rigor as application code

::left::

<div v-click>

## Infrastructure as Software
- Version controlled
- Code reviews
- Testing enabled
- Clear history
- Team collaboration

</div>

<div v-click>

## Declarative Definitions
- Describe desired state
- System handles "how"
- Predictable results
- Self-documenting

</div>

::right::

<div v-click>

## Automation First
- Repeatable processes
- Consistent results
- Reduced human error
- Scalable operations

</div>

<div v-click>

## Immutable Infrastructure
- No manual changes
- Replace vs modify
- Versioned states
- Easy rollbacks

</div>

<!--
# Speaker Notes

Connect to their experience:
- "Like your git workflow"
- "Similar to unit tests"
- "Think declarative like SQL"
- "Remember containers vs VMs"

Ask about principles:
- "Which seems most valuable?"
- "Which might be challenging?"
- "Used any of these in projects?"
-->
---
layout: two-cols-header
---

# IaC Tools Landscape

Different tools for different infrastructure needs

::left::

<div v-click>

## General Purpose
- Terraform - Multi-cloud
- Pulumi - Multi-language
- CloudFormation - AWS
- ARM Templates - Azure

</div>

::right::

<div v-click>

## Specialized Tools
- Ansible - Configuration
- Kubernetes - Containers
- Helm - K8s packages
- CDK - Cloud Development

</div>

<!--
# Speaker Notes

Key points:
- Different tools solve different problems
- Can be complementary
- We'll focus on Pulumi because:
  * Real programming languages
  * Strong typing
  * Familiar development experience

Questions to ask:
- "Used any of these tools?"
- "Seen them in internships?"
-->
---
layout: center
---

# The Development Workflow

<div class="workflow">
  <div v-click class="step">
    <div class="icon">👩‍💻</div>
    <div class="text">Local Development</div>
    <div class="code-box">
      main.ts
    </div>
  </div>

  <div v-click class="arrow">→</div>

  <div v-click class="step">
    <div class="icon">🔍</div>
    <div class="text">Preview Changes</div>
    <div class="detail">pulumi preview</div>
  </div>

  <div v-click class="arrow">→</div>

  <div v-click class="step">
    <div class="icon">📤</div>
    <div class="text">Create PR</div>
    <div class="detail">git push</div>
  </div>
</div>

<style>
.workflow {
  @apply flex items-center justify-center gap-8 mt-12;
}
.step {
  @apply flex flex-col items-center;
}
.icon {
  @apply text-4xl mb-4;
}
.text {
  @apply text-xl font-bold;
}
.detail {
  @apply text-sm opacity-75 mt-2;
}
.arrow {
  @apply text-2xl text-blue-400;
}
.code-box {
  @apply font-mono text-sm bg-gray-800 rounded p-2 mt-2;
}
</style>

<!--
# Speaker Notes

First part of the workflow:
- Start with local development
- Just like regular code
- Preview before pushing
- Fast feedback loop

Questions:
- "Familiar workflow from software dev?"
- "What would you expect to see in preview?"
-->

---
layout: center
---

# Team Review Process

<div class="workflow">
  <div v-click class="step">
    <div class="icon">👥</div>
    <div class="text">Team Review</div>
    <div class="detail">Code Review + Plan</div>
  </div>

  <div v-click class="arrow">→</div>

  <div v-click class="step">
    <div class="icon">🤖</div>
    <div class="text">CI Validation</div>
    <div class="detail">Tests & Security</div>
  </div>

  <div v-click class="arrow">→</div>

  <div v-click class="step">
    <div class="icon">🚀</div>
    <div class="text">Deploy</div>
    <div class="detail">pulumi up</div>
  </div>
</div>

<div v-click class="mt-12 text-center">
  <div class="text-xl mb-2">Just like your application code!</div>
  <div class="text-sm opacity-75">Same tools, same process, same confidence</div>
</div>

<style>
.workflow {
  @apply flex items-center justify-center gap-8 mt-12;
}
.step {
  @apply flex flex-col items-center;
}
.icon {
  @apply text-4xl mb-4;
}
.text {
  @apply text-xl font-bold;
}
.detail {
  @apply text-sm opacity-75 mt-2;
}
.arrow {
  @apply text-2xl text-blue-400;
}
</style>

<!--
# Speaker Notes

Second part focused on team:
- Standard PR process
- Automated validation
- Confident deployments
- Just like app development

Key points:
- Infrastructure changes get same rigor
- Multiple eyes on changes
- Automated safety checks
- Clear deployment process

Demo teaser:
- "We'll see this in action soon"
- "You'll create your first PR"
-->
---
layout: two-cols-header
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
- But show they're manageable
- Most are one-time costs
- Common to all new tech adoption

Key message:
"Benefits compound over time, challenges decrease"

Ask:
"Which benefit interests you most?"
"Which challenge concerns you?"
-->