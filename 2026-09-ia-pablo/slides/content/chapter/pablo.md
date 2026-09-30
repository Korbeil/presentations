# Enter PABLO

**P**ersonal **A**ssistant for **B**oring **L**ogic & **O**perations

<div class="mt-10 text-lg space-y-6">

- <mdi-console class="text-[#e9ce37]"/> A **Symfony console application**: the `pablo` CLI, the console, and a read-only web dashboard (port **8321**)
- <mdi-timer-outline class="text-[#e9ce37]"/> A **systemd / launchd scheduler** wakes it every **5 minutes** — state polling every 10, worktree sync every 12
- <mdi-key-remove class="text-[#e9ce37]"/> **No tokens stored**: everything through already-authenticated CLIs (`gh`, `acli`, `linear`, `openchamber`, `opencode`) — `pablo system:doctor` diagnoses what is missing
- <mdi-swap-horizontal class="text-[#e9ce37]"/> `AgentLauncherInterface` keeps the **ADE swappable** — it already swapped Orca → OpenChamber

</div>
