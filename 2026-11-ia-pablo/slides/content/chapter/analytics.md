# Des analytics détaillées

<div class="mt-4 grid grid-cols-[3fr_2fr] gap-8">

<div>

```bash
pablo stats --by agent --days 30
```

```text
Agent          Runs  Avg time  Total  Hit%   User wait
-------------  ----  --------  -----  -----  ---------
ci-analyst     44    1m        8.4M   83.8%  7h15m
task-analyst   37    1m        7.8M   84.8%  8h9m
pr-feedback    15    2m        2.1M   77.2%  42h33m
```

```bash
pablo stats --by task          # agent | project | model | task
pablo task:history my-branch   # la timeline d'une tâche
```

</div>

<div class="text-base space-y-3">

- <mdi-timer-sand class="text-[#e9ce37]"/> **durée de vie** des tâches : moyenne, p50, p90, taux de merge
- <mdi-robot-outline class="text-[#e9ce37]"/> **chaque run** : tokens in / out / cache, **cache hit rate**, coût, modèle
- <mdi-account-clock class="text-[#e9ce37]"/> **user wait** : combien de temps le résultat m'a attendu
- <mdi-sync class="text-[#e9ce37]"/> **temps passé par état** : beaucoup d'entrées en `ci-red` = boucles de rework
- <mdi-chart-bar class="text-[#e9ce37]"/> les mêmes chiffres en graphes dans le dashboard (`/analytics`)

</div>

</div>

<div class="mt-6 text-sm opacity-70">
<mdi-shield-lock-outline class="text-[#e9ce37]"/> Tout reste en local dans <code>~/.pablo/analytics/</code> (un JSONL par mois). Aucun prompt stocké : juste sa longueur et une empreinte.
</div>

<style>
.slidev-layout pre { font-size: 11px !important; line-height: 16px !important; }
</style>

<!--
Chiffres réels, mes 30 derniers jours (abonnement : le coût reste quasi nul, les tokens sont bien réels).
Ce qui m'a surpris : le run prend 1 à 2 minutes, mais le résultat m'attend des heures. Le goulot, c'est moi — c'est exactement l'argument « brain time ».
pr-feedback attend 42 h : les reviews arrivent en fin de journée, je les traite le lendemain.
Les tokens viennent d'OpenCode, des transcripts Claude Code ou des sessions Copilot, une fois le run terminé.
-->
