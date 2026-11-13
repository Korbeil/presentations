# Des analytics détaillées

<div class="mt-4 flex justify-center">
<img src="/images/pablo-analytics.png" alt="Page Analytics du dashboard PABLO : KPIs, runs par agent, top des tâches par tokens, tokens et coût par modèle" class="rounded-lg shadow-lg" style="max-height: 350px" />
</div>

<div class="mt-3 text-center text-lg opacity-80">
<code>pablo web</code> → <code>/analytics</code>
</div>

<!--
Tout ce qui est dans le dashboard est aussi dispo en CLI :
- pablo stats (30 derniers jours) : durée de vie des tâches (moyenne, p50, p90, taux de merge), runs par agent, temps passé par état
- pablo stats --by agent|project|model|task, --format json|csv
- pablo task:history <branche> : la timeline d'une tâche (états, runs, tokens, coût)

Ce qu'on voit : tokens in / out / cache, cache hit rate (~84 %), coût, modèle. Chiffres réels, mes 30 derniers jours (abonnement : le coût reste quasi nul, les tokens sont bien réels). Noms de projets floutés.
Ce qui m'a surpris : le run prend 1 à 2 minutes, mais le résultat m'attend des heures (« user wait »). Le goulot, c'est moi : exactement l'argument « brain time ».
Beaucoup d'entrées en ci-red ou request-changes = boucles de rework.
Tout reste en local dans ~/.pablo/analytics/ (un JSONL par mois). Aucun prompt stocké : juste sa longueur et une empreinte.
-->
