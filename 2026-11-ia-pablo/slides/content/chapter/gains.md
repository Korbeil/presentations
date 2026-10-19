# La productivité, sans mentir

<div class="mt-8 grid grid-cols-3 gap-8">

<div class="stat">
<div class="bignum">½<small>&thinsp;journée</small></div>
<div class="cap">de contexte absorbée par ticket — <code>task-analyst</code> / <code>task-feedback</code>, sans équipe « focus »</div>
</div>

<div class="stat">
<div class="bignum">20<small>&thinsp;min</small></div>
<div class="cap">de tri vers Slack en moins — <code>/github-awaiting-review</code>. Le vrai gain : ma concentration</div>
</div>

<div class="stat">
<div class="bignum">0</div>
<div class="cap">conflit de merge à gérer moi-même — <code>/milestone-build</code>. Peu de minutes gagnées, mais plus de tri</div>
</div>

</div>

<div class="mt-10 text-base space-y-2">

- `pr-review-planner` : chaque commentaire de review arrive avec son contexte et ses options
- l'ADE lui-même : Jira pour m'assigner, GitHub pour relire les autres, Slack pour partager — tout le reste vit dans l'ADE

</div>

<div class="mt-6 text-sm opacity-60">
Ce qui coince encore : l'infra locale. Plusieurs copies du même site = conflits Docker, et un seul Traefik possible.
</div>

<!--
Les gains ne sont pas uniformes : les qualifier honnêtement, c'est la moitié de l'histoire.
/github-milestone-triage : même gain que /github-awaiting-review.
Docker : conteneurs préfixés par le nom du worktree, mais Traefik résiste.
-->
