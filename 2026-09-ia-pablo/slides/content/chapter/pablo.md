# Enter PABLO

**P**ersonal **A**ssistant for **B**oring **L**ogic & **O**perations

<div class="grid grid-cols-2 gap-8 mt-2">

<div class="text-base">

- <mdi-console class="text-[#e9ce37]"/> A **Symfony console application**: the `pablo` CLI, the console, and a read-only web dashboard (port **8321**)
- <mdi-timer-outline class="text-[#e9ce37]"/> A **systemd / launchd scheduler** wakes it every **5 minutes** — state polling every 10, worktree sync every 12
- <mdi-key-variant-remove class="text-[#e9ce37]"/> **No tokens stored**: everything through already-authenticated CLIs (`gh`, `acli`, `linear`, `openchamber`, `opencode`) — `pablo system:doctor` diagnoses what is missing
- <mdi-swap-horizontal class="text-[#e9ce37]"/> `AgentLauncherInterface` keeps the **ADE swappable** — it already swapped Orca → OpenChamber

</div>

<div class="text-center">

<div class="rounded-lg bg-#2b2b2a text-white p-6 mt-4 text-lg">
One question, on a loop:

<br>

*Given the state of this pull request, is there something an agent should be doing — and if so, which one?*
</div>

<div class="mt-4 text-base opacity-80">
…then it launches that agent through the ADE CLI,<br>in the right worktree, exactly as I would have.
</div>

```yaml
# why PHP in 2026?
# fastest language I think in,
# and the only user is me.
```

</div>

</div>
