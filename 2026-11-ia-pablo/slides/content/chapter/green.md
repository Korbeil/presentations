# Une CI verte est une politique, pas un fait

Ma première version : rouge sur échec, verte si tout passe, *pending* sinon. Fonctionnait partout… sauf sur le projet où j'avais le plus besoin de PABLO.

Ce projet tourne sur **CircleCI**, qui publie ses gates de déploiement sous forme de *status contexts* GitHub — des gates manuelles, `PENDING` pour toujours sur des branches où personne n'a cliqué, ou qui arrivent en `ACTION_REQUIRED` (comptées comme des échecs par ma règle première). Alors « Est-ce que la CI est verte ? » n'était jamais oui.

```yaml
ci:
  ignore_checks: ["approval"]
```

<div class="mt-3 text-base space-y-1">

- tout check dont le nom, le workflow ou le status context contient ce substring est <b>retiré de la question</b> : ni rouge, ni pending pour toujours
- reste intentionnellement bête : substring match, et un repo sans check est déclaré vert
- GitHub appelle ça des « checks » — c'est un tas bruyant de tests unitaires, de gates manuelles et de bots bavards. Aucun outil ne peut deviner magiquement ; <b>la décision est poussée dans le YAML du projet</b>

</div>
