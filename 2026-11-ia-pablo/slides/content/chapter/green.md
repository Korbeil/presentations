# Une CI verte est une politique, pas un fait

Ma première règle : rouge sur échec, verte si tout passe, *pending* sinon. Elle marchait partout… sauf sur le projet où j'avais le plus besoin de PABLO : CircleCI y publie ses gates de déploiement manuelles comme des checks GitHub, `PENDING` pour toujours ou `ACTION_REQUIRED`. La CI n'était jamais verte.

<div class="mt-4 grid grid-cols-[1fr_1.1fr] gap-6 items-start">

<div>

```yaml
ci:
  ignore_checks: ["approval"]
```

<div class="mt-3 text-base space-y-1">

- tout check dont le nom, le workflow ou le status context contient ce mot est <b>retiré de la question</b>
- volontairement bête : un substring, et un repo sans check est vert
- **deux gates, un mot** — la décision vit dans le YAML du projet

</div>

</div>

<img src="/images/github-approval-gates.png" class="rounded-lg shadow" alt="Gates d'approbation CircleCI dans les checks GitHub" />

</div>

<!--
Ce que GitHub appelle des « checks », c'est un tas bruyant de tests, de gates manuelles et de bots bavards. Aucun outil ne peut deviner lesquels comptent pour une branche donnée.
-->
