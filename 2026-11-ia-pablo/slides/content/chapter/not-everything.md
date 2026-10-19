# Tout ne mérite pas un LLM

`/github-awaiting-review` et `/github-milestone-triage` : appeler `gh`, lire les PRs ouvertes, demander à un LLM un message Slack poli. Ça sentait la magie. **Elles n'ont pas survécu** : aujourd'hui, c'est du PHP classique qui lit le cache du poller.

<div class="mt-8 grid grid-cols-[1fr_auto_1fr] gap-10 items-end">

<div class="stat">
<div class="bignum">~14 400</div>
<div class="cap">lignes de PHP dans <code>app/src/</code> — la plomberie</div>
</div>

<div class="text-3xl font-300 opacity-40 pb-6">vs</div>

<div class="stat">
<div class="bignum">~1 100</div>
<div class="cap">lignes de markdown dans <code>opencode/</code> — l'intelligence</div>
</div>

</div>

<div class="mt-10 rounded-lg bg-#2b2b2a text-white p-4 text-base">
Un outil bâti pour orchestrer des agents IA, c'est en fait : des timestamps, des file locks, du parsing de sortie CLI et une table de transitions autorisées.<br>
<b>L'intelligence tient dans cinq agents en markdown ; le reste est de la plomberie qui décide quand ouvrir le robinet.</b>
</div>
