# Voici PABLO

**P**ersonal **A**ssistant for **B**oring **L**ogic &amp; **O**perations

<div class="mt-8 text-lg space-y-4">

- <mdi-console class="text-[#e9ce37]"/> Une **application Symfony console** : le CLI `pablo` et un dashboard web en lecture seule (`pablo web`, port 8321)
- <mdi-timer-outline class="text-[#e9ce37]"/> Un **scheduler systemd / launchd** le réveille toutes les **5 min** — polling toutes les 10, sync des worktrees toutes les 12, réglables dans le YAML du projet ; un échec réessaie simplement au tour suivant
- <mdi-key-remove class="text-[#e9ce37]"/> **Aucun token stocké** : tout passe par des CLIs déjà authentifiées (`gh`, `acli`, `linear`, `opencode`…) ; `pablo system:doctor` dit ce qui manque *avant* qu'un cron échoue à 3 h du matin
- <mdi-robot-outline class="text-[#e9ce37]"/> **Une seule étape confiée à un LLM** : `/pablo-commit-and-pr` écrit le commit et la description de PR, passe la tâche en `draft`, et rend la main à PABLO

</div>

<div class="mt-8 text-base opacity-70">
Pourquoi PHP pour un démon en 2026 ? Le langage dans lequel je pense le plus vite — et le seul utilisateur, c'est moi.
</div>

<!--
L'acronyme est venu après le nom, mais « boring » est le mot honnête : rien de ce que fait PABLO n'est malin.
Les timestamps de dernier passage ne sont écrits qu'en cas de succès.
-->
