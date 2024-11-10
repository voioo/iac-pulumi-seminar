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
- Setup for demo
-->

---
layout: center
hideInToc: true
---

# The Modern Challenge of Growth
Building and scaling your first application

<div class="flex gap-12">
  <div v-click class="challenge-box">
    <div class="text-xl mb-2">Initial Setup</div>
    <ul>
      <li>Small team (3 developers)</li>
      <li>Promising app with database</li>
      <li>Multiple environments needed</li>
    </ul>
  </div>

  <div v-click class="challenge-box">
    <div class="text-xl mb-2">Growing Pains</div>
    <ul>
      <li>Manual Azure setup</li>
      <li>Configuration complexity</li>
      <li>Team coordination needed</li>
    </ul>
  </div>
</div>

<style>
.challenge-box {
  @apply p-4 rounded bg-gray-100 bg-opacity-10;
}
</style>

<!--
# Presenter Notes
- Introduce real-world scenario
- Connect to their experiences
- Set up for infrastructure solutions
- Bridge to next section
-->

---
layout: center
hideInToc: true
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
  (demo)
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
hideInToc: true
---

# Issues with Manual Management
Why clicking doesn't scale

<div class="grid grid-cols-2 gap-8 mt-8">
  <div v-click class="issue-box">
    <div class="text-xl mb-2">Process Issues</div>
    <ul>
      <li>Hard to replicate</li>
      <li>No history tracking</li>
      <li>Error-prone</li>
    </ul>
  </div>

  <div v-click class="issue-box">
    <div class="text-xl mb-2">Team Issues</div>
    <ul>
      <li>Team coordination challenges</li>
      <li>Tribal knowledge</li>
      <li>Configuration drift</li>
    </ul>
  </div>
</div>

<div v-click class="mt-12 text-center text-xl bg-blue-500 bg-opacity-10 p-4 rounded">
  So how can we do this better?
</div>

<style>
.issue-box {
  @apply p-4 rounded bg-gray-100 bg-opacity-10;
}
</style>

---
layout: two-cols-header
hideInToc: true
---

---
layout: two-cols-header
hideInToc: true
---

# Core IaC Principles
Infrastructure managed with the same rigor as application code

::left::

<div v-click class="principle-box">
  <div class="text-xl mb-2">Infrastructure as Software</div>
  <ul>
    <li>Version controlled</li>
    <li>Code reviews</li>
    <li>Testing enabled</li>
    <li>Clear history</li>
    <li>Team collaboration</li>
  </ul>
</div>

::right::

<div v-click class="principle-box">
  <div class="text-xl mb-2">Automation First</div>
  <ul>
    <li>Repeatable processes</li>
    <li>Consistent results</li>
    <li>Reduced human error</li>
    <li>Scalable operations</li>
  </ul>
</div>

<style>
.principle-box {
  @apply p-4 rounded bg-gray-100 bg-opacity-10;
}
</style>

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
hideInToc: true
---

# Core IaC Principles #2
Declarative definitions and immutable infrastructure

::left::

<div v-click class="principle-box">
  <div class="text-xl mb-2">Declarative Definitions</div>
  <ul>
    <li>Describe desired state</li>
    <li>System handles "how"</li>
    <li>Predictable results</li>
    <li>Self-documenting</li>
  </ul>
</div>

::right::

<div v-click class="principle-box">
  <div class="text-xl mb-2">Immutable Infrastructure</div>
  <ul>
    <li>No manual changes</li>
    <li>Replace vs modify</li>
    <li>Versioned states</li>
    <li>Easy rollbacks</li>
  </ul>
</div>

<style>
.principle-box {
  @apply p-4 rounded bg-gray-100 bg-opacity-10;
}
</style>

---
layout: two-cols-header
hideInToc: true
---

# IaC Tools Landscape
Different tools for different infrastructure needs

::left::

<div v-click class="tool-box">
  <div class="text-xl mb-2">General Purpose</div>
  <ul>
    <li><strong>Terraform</strong> - Multi-cloud</li>
    <li><strong>Pulumi</strong> - Multi-language</li>
    <li><strong>CloudFormation</strong> - AWS</li>
    <li><strong>ARM Templates</strong> - Azure</li>
  </ul>
</div>

::right::

<div v-click class="tool-box">
  <div class="text-xl mb-2">Specialized Tools</div>
  <ul>
    <li><strong>Ansible</strong> - Configuration</li>
    <li><strong>Chef</strong> - VM management</li>
    <li><strong>Kubernetes</strong> - Containers</li>
    <li><strong>Helm</strong> - K8s packages</li>
  </ul>
</div>

<style>
.tool-box {
  @apply p-4 rounded bg-gray-100 bg-opacity-10;
}
</style>

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
- "Seen them in internships/jobs?"
-->
---
layout: center
hideInToc: true
---

# The Development Workflow
From local development to deployment

<div class="workflow">
  <div v-click class="step">
    <div class="icon">👩‍💻</div>
    <div class="text">Local Development</div>
    <div class="code-box">
      main.cs
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
-->

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
hideInToc: true
---

# Team Review Process

<div class="workflow">
  <div v-click class="step">
    <div class="icon">👥</div>
    <div class="text">Team Review</div>
    <div class="detail">Code Review + Preview</div>
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
-->