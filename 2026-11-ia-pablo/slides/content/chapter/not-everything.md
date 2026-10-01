# Pas tout mérite un LLM

Deux de mes anciennes *commands* IA : appeler `gh`, lire les PRs ouvertes, demander à un LLM d'écrire un message Slack poli pour la review et la QA. Ça sentait la magie.

**Elles n'ont pas survécu.** Aujourd'hui : `pablo show:prs` — un script PHP classique qui lit le cache du poller et imprime le même markdown prêt pour Slack.

<div class="mt-8 grid grid-cols-2 gap-10 text-lg text-center">

<div>

### Code PHP (plomberie)

<div class="text-3xl font-bold">~13 400</div>
<div class="text-sm opacity-70">lignes dans `app/src/`</div>

</div>

<div>

### Prompts & agents (l'intelligence)

<div class="text-3xl font-bold">~1 200</div>
<div class="text-sm opacity-70">lignes de markdown dans `opencode/`</div>

</div>

</div>

<div class="mt-10 rounded-lg bg-#2b2b2a text-white p-4 text-base">
Un outil bâti pour orchestrer des agents IA s'avère être : des timestamps, des file locks, du parsing de sortie CLI et une table de transitions autorisées.<br>
<b>L'intelligence est dans cinq fichiers markdown ; tout le reste est de la plomberie peu glamour qui décide quand ouvrir le robinet.</b>
</div>
