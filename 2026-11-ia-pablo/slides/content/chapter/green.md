---
layout: split
---

# Une CI verte est une politique, pas un fait

<div class="text-base">
Ma première règle marchait partout… sauf là où j'en avais le plus besoin : CircleCI publie ses gates de déploiement manuelles comme des checks GitHub, <code>PENDING</code> pour toujours.
</div>

```yaml
ci:
  ignore_checks: ["approval"]
```

<div class="mt-3 text-base space-y-1">

- tout check dont le nom contient ce mot est <b>retiré de la question</b>
- volontairement bête : un substring, et un repo sans check est vert
- **deux gates, un mot** — la décision vit dans le YAML du projet

</div>

::right::

<img src="/images/github-approval-gates.png" alt="Gates d'approbation CircleCI dans les checks GitHub" />

<div class="mt-6 text-lg font-600 text-center">« Est-ce que la CI est verte ? »<br>n'était jamais oui.</div>

<!--
Les gates arrivent aussi en ACTION_REQUIRED, que ma première règle comptait comme un échec.
Ce que GitHub appelle des « checks », c'est un tas bruyant de tests, de gates manuelles et de bots bavards. Aucun outil ne peut deviner lesquels comptent pour une branche donnée.
-->
