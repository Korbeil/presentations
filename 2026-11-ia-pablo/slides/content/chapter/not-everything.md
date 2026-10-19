# Tout ne mérite pas un LLM

`/github-awaiting-review` et `/github-milestone-triage` : appeler `gh`, lire les PRs ouvertes, demander à un LLM un message Slack poli pour la review et la QA. Ça sentait la magie.

**Elles n'ont pas survécu.** Aujourd'hui, c'est du PHP classique qui lit le cache du poller et sort le même markdown prêt pour Slack.

<div class="mt-8 grid grid-cols-2 gap-10 text-lg text-center">

<div>

### Code PHP (plomberie)

<div class="text-3xl font-bold">~14 400</div>
<div class="text-sm opacity-70">lignes dans <code>app/src/</code></div>

</div>

<div>

### Prompts & agents (l'intelligence)

<div class="text-3xl font-bold">~1 100</div>
<div class="text-sm opacity-70">lignes de markdown dans <code>opencode/</code></div>

</div>

</div>

<div class="mt-10 rounded-lg bg-#2b2b2a text-white p-4 text-base">
Un outil bâti pour orchestrer des agents IA, c'est en fait : des timestamps, des file locks, du parsing de sortie CLI et une table de transitions autorisées.<br>
<b>L'intelligence tient dans cinq agents en markdown ; le reste est de la plomberie peu glamour qui décide quand ouvrir le robinet.</b>
</div>
