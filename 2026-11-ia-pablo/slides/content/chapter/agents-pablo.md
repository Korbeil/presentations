# Les agents de PABLO — un état, un agent

<div class="mt-4 text-base space-y-3">

- <mdi-magnify class="text-[#e9ce37]"/> **task-analyst** ← <code>in-progress</code> — le ticket, ses parents, les PRs liées, le code concerné → un résumé et un plan d'action. Une seule fois par tâche
- <mdi-alert-circle-outline class="text-[#e9ce37]"/> **ci-analyst** ← <code>ci-red</code> — récupère les checks en échec et leurs logs, relie chaque échec au code responsable, propose un plan de correction
- <mdi-comment-quote class="text-[#e9ce37]"/> **pr-feedback** ← <code>request-changes</code> — les commentaires de review deviennent un plan de correction ; la PR repasse en `draft`
- <mdi-reply-all-outline class="text-[#e9ce37]"/> **task-feedback** ← <code>testing-failed</code> — le retour de QA confronté à la PR, classé remarque par remarque, avec une réponse prête pour le ticket
- <mdi-source-merge class="text-[#e9ce37]"/> **rebase-conflict-resolver** ← le sync de rebase, hors schéma — quand git abandonne sur un conflit

</div>

<div class="mt-6 rounded-lg bg-#f7e9a0 p-4 text-base">
Les quatre premiers sont <b>en lecture seule</b> : ils analysent, jamais de code touché.
</div>

<!--
Les états jaunes du schéma (ci-red, request-changes, testing-failed) = les trois moments où PABLO me ramène du travail à faire.
in-progress en vert = le point de départ, déclenché par task:start.
-->
