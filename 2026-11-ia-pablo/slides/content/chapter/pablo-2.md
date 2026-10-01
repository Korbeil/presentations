# Enter PABLO

**P**ersonal **A**ssistant for **B**oring **L**ogic &amp; **O**perations

<div class="mt-10 text-lg space-y-5">

- <mdi-console class="text-[#e9ce37]"/> Une **application Symfony console** : le CLI `pablo`, les commandes console, un dashboard web en lecture seule (port **8321**)
- <mdi-timer-outline class="text-[#e9ce37]"/> Un **scheduler systemd / launchd** le réveille toutes les **5 minutes** — polling d'état toutes les 10, sync des worktrees toutes les 12 — tout ça dans le YAML de chaque projet ; les timestamps de dernier passage ne sont écrits qu'en cas de **succès**
- <mdi-key-remove class="text-[#e9ce37]"/> **Aucun token stocké** : tout passe par des CLIs déjà authentifiées (`gh`, `acli`, `linear`, `openchamber`, `opencode`) — rien à faire tourner ni à fuiter ; `pablo system:doctor` diagnostique ce qui manque *avant* une erreur de cron à 3 h du matin
- <mdi-swap-horizontal class="text-[#e9ce37]"/> `AgentLauncherInterface` : PABLO ne demande jamais qu'un agent en worktree et un retour de fin de run — <b>l'ADE est un détail interchangeable</b> *(déjà échangé une fois : Orca → OpenChamber)*

</div>

<div class="mt-8 text-base opacity-80">
Une seule exception à *« PABLO n'utilise pas de LLM »* : <code>/pablo-commit-and-pr</code> — l'agent écrit commit + description de PR (la seule étape où un agent bat du code classique), puis <b>rend la main à PABLO</b>, qui passe la tâche en état <code>draft</code> et reprend la main.
</div>
