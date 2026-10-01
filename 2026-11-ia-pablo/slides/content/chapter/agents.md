# Mes agents — la partie où j'ai le plus investi

<div class="mt-4 text-base space-y-1.5">

- <mdi-hammer class="text-[#e9ce37]"/> **build** *(built-in)* — le <b>seul</b> agent autorisé à toucher du code
- <mdi-map-outline class="text-[#e9ce37]"/> **plan** / **heavy-plan** — planifier ; le second sur un modèle Opus pour le gros et le risqué
- <mdi-magnify class="text-[#e9ce37]"/> **task-analyst** — prend un lien Jira, lit le ticket, ses parents, les PRs ouvertes, et rend ce qui est demandé + ce qui existe déjà + un plan d'action. **Point de départ 95 % du temps** — jusqu'à une demi-journée de contexte absorbée par changement de domaine
- <mdi-reply-all-outline class="text-[#e9ce37]"/> **task-feedback** — QA a trouvé une erreur sur ma PR : relit le ticket, retrouve la PR, checkout la branche, tente de comprendre le feedback et formule les premières hypothèses
- <mdi-comment-quote class="text-[#e9ce37]"/> **pr-review-planner** — les commentaires de review deviennent une **checklist à exécuter**, plus une séance d'archéologie
- <mdi-glasses class="text-[#e9ce37]"/> **pr-reviewer** — je relis moi-même, en parallèle un agent relit ce que j'ai (peut-être) raté

</div>

<div class="mt-6 rounded-lg bg-#f7e9a0 p-4 text-base">
Tous des agents d'<b>analyse</b> : ils lisent, résument, planifient — <b>mais ne touchent jamais le code.</b> La contrainte est dans la définition de l'agent même.
</div>
