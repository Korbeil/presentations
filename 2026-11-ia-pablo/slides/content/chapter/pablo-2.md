# Voici PABLO

**P**ersonal **A**ssistant for **B**oring **L**ogic &amp; **O**perations

<div class="mt-6 text-base space-y-3">

- <mdi-console class="text-[#e9ce37]"/> Une **application Symfony console** : le CLI `pablo` et un dashboard web en lecture seule (`pablo web`, port 8321)
- <mdi-key-remove class="text-[#e9ce37]"/> **Aucun token stocké** : tout passe par des CLIs déjà authentifiées (`gh`, `acli`, `linear`, `opencode`…) ; `pablo system:doctor` dit ce qui manque *avant* qu'un cron échoue à 3 h du matin
- <mdi-robot-outline class="text-[#e9ce37]"/> **Une seule étape confiée à un LLM** : `/pablo-commit-and-pr` écrit le commit et la description de PR, passe la tâche en `draft`, et rend la main à PABLO

</div>

<div class="mt-8 grid grid-cols-3 gap-8">

<div class="stat">
<div class="bignum">5<small>&thinsp;min</small></div>
<div class="cap">le scheduler systemd / launchd réveille PABLO</div>
</div>

<div class="stat">
<div class="bignum">10<small>&thinsp;min</small></div>
<div class="cap">polling de l'état de chaque PR</div>
</div>

<div class="stat">
<div class="bignum">12<small>&thinsp;h</small></div>
<div class="cap">sync des worktrees sur la branche primaire</div>
</div>

</div>

<!--
L'acronyme est venu après le nom, mais « boring » est le mot honnête : rien de ce que fait PABLO n'est malin.
Cadences réglables dans le YAML du projet ; les timestamps de dernier passage ne sont écrits qu'en cas de succès, donc un échec réessaie au tour suivant.
Pourquoi PHP pour un démon en 2026 ? Le langage dans lequel je pense le plus vite, et le seul utilisateur, c'est moi.
-->
