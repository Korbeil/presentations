---
layout: two-cols
---

# What actually changed

<div class="mt-2 text-base">

> **I did not check less, I stopped checking by myself.**

CI goes red at 11pm → the poller notices within 10 minutes → `ci-analyst` runs in the right worktree → by morning, the diagnosis is waiting.

A full task:

```bash
pablo task:start https://acme.atlassian.net/browse/XXX-123
# work with the agent
/pablo-commit-and-pr
# …stop thinking about it
```

<div class="mt-4 rounded-lg bg-#2b2b2a text-white p-3">
**Brain time is the resource.** PABLO is a cognitive shield: I stopped being a human router for my own tasks.
</div>

</div>

::right::

<div class="mt-16 text-lg">

**PABLO is public** <mdi-github class="text-[#e9ce37]"/>

<https://github.com/korbeil/pablo>

<span class="text-sm opacity-70">PHP 8.4+ · `./bin/install.sh` · `pablo system:doctor`</span>

<br>
<br>

**Read the whole story**

<mdi-book-open-variant class="text-[#e9ce37]"/> [The Agent Development Environment: A New Unit of Work](https://jolicode.com/blog/the-agent-development-environment-a-new-unit-of-work)

<mdi-book-open-variant class="text-[#e9ce37]"/> [From an ADE to an Orchestrator: Building PABLO](https://jolicode.com/blog/from-an-ade-to-an-orchestrator-building-pablo)

<br>

# Merci !

</div>
