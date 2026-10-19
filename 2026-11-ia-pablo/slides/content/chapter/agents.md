# Mes agents — la partie où j'ai le plus investi

<div class="mt-4 text-base space-y-2">

- <mdi-hammer class="text-[#e9ce37]"/> **build** *(built-in)* — le <b>seul</b> agent autorisé à toucher du code
- <mdi-map-outline class="text-[#e9ce37]"/> **plan** / **heavy-plan** — planifier ; le second sur un modèle plus puissant, pour le gros et le risqué
- <mdi-magnify class="text-[#e9ce37]"/> **task-analyst** — un lien de ticket → le ticket, ses parents, les PRs liées, le code concerné → un résumé et un plan d'action. **Mon point de départ 95 % du temps**
- <mdi-reply-all-outline class="text-[#e9ce37]"/> **task-feedback** — QA a trouvé une erreur : retrouve la PR, checkout la branche, formule les premières hypothèses
- <mdi-comment-quote class="text-[#e9ce37]"/> **pr-review-planner** — les commentaires de review deviennent une **checklist**, plus une séance d'archéologie
- <mdi-glasses class="text-[#e9ce37]"/> **pr-reviewer** — je relis moi-même ; en parallèle, un agent relit ce que j'ai (peut-être) raté

</div>

<div class="mt-6 rounded-lg bg-#f7e9a0 p-4 text-base">
Tous sauf <code>build</code> sont des agents d'<b>analyse</b> : ils lisent, résument, planifient — <b>mais ne touchent jamais le code.</b><br>
Pas besoin du modèle le plus cher : un modèle <b>rapide, pas cher, à basse température</b> fait le travail.
</div>

<div class="mt-4 text-sm opacity-70">
Mon agent CLI : OpenCode — mais tout se transpose à Claude Code, Codex, etc.
</div>

<!--
task-analyst = l'agent dans lequel j'ai le plus investi, prompt amélioré itération après itération.
Tous les prompts sont dans un gist (lien dans l'article).
-->
