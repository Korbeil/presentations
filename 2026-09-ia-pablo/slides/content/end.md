---
layout: two-cols
---

# What actually changed

<div class="mt-2 text-base">

> **I did not check less, I stopped checking by myself.**

- <mdi-check-circle-outline class="text-[#e9ce37]"/> CI goes red at 11pm
- <mdi-timer-outline class="text-[#e9ce37]"/> the poller notices within 10 minutes
- <mdi-robot-outline class="text-[#e9ce37]"/> `ci-analyst` runs in the right worktree
- <mdi-weather-sunset-up class="text-[#e9ce37]"/> by morning, the diagnosis is waiting

A full task:

```bash {lines:false}
pablo task:start \
  https://acme.atlassian.net/browse/XXX-123
# …work with the agent
/pablo-commit-and-pr
# …stop thinking about it
```

<div class="mt-2 rounded-lg bg-#2b2b2a text-white p-3 text-sm">
<b>Brain time is the resource.</b><br>PABLO is a cognitive shield: I stopped being a human router for my own tasks.
</div>

</div>

::right::

<div class="mt-10 text-base">

**PABLO is public** <mdi-github class="text-[#e9ce37]"/>

<https://github.com/korbeil/pablo>

<span class="text-sm opacity-70">PHP 8.4+ · <code>./bin/install.sh</code> · <code>pablo system:doctor</code></span>

</div>
