# La productivité, sans mentir

<div class="mt-6 text-lg space-y-4">

- **Spectaculaire** — `task-analyst` / `task-feedback` : pas d'équipe « focus », n'importe qui sur n'importe quoi ; l'agent absorbe jusqu'à une demi-journée de contexte par ticket
- **Spectaculaire aussi** — `pr-review-planner` : chaque commentaire arrive avec son contexte et ses options
- **Marginal en minutes, immense en attention** — `/github-awaiting-review` &amp; `/github-milestone-triage` : jusqu'à 20 min de tri vers Slack ; le vrai gain, c'est que je ne casse plus ma concentration
- **Petit** — `/milestone-build` : peu de minutes gagnées, mais plus de conflits de merge ni de tri des PRs à faire
- **L'ADE lui-même** : Jira pour m'assigner, GitHub pour relire les autres, Slack pour partager. Tout le reste vit dans l'ADE

</div>

<div class="mt-8 text-base opacity-70">
Ce qui coince encore : l'infra locale. Plusieurs copies du même site = conflits Docker, et un seul Traefik possible.
</div>

<!--
Les gains ne sont pas uniformes : les qualifier honnêtement, c'est la moitié de l'histoire.
Docker : conteneurs préfixés par le nom du worktree, mais Traefik résiste.
-->
