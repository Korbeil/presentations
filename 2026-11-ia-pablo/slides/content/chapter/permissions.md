# Read-only par construction, pas par promesse

Chaque appel d'outil est résolu en `allow`, `ask` ou `deny` — dans le frontmatter de l'agent :

```yaml
---
description: Analyser un ticket et produire un plan d'action
mode: subagent
permissions:
  - { action: edit,  resource: "*",          effect: deny }  # edit, write, patch
  - { action: shell, resource: "*",          effect: deny }  # par défaut : rien ne s'exécute
  - { action: shell, resource: "git *",      effect: allow } # ... sauf git
  - { action: shell, resource: "git push *", effect: deny }  # ... mais jamais de push
---
```

<div class="mt-4 text-base space-y-1">

- par défaut, **tout est `allow`** : un agent d'analyse n'est read-only que si on le dit
- **la dernière règle qui matche gagne** : le cas général d'abord, les exceptions ensuite — l'ordre est tout
- `"git *"` matche aussi `git` tout seul ; `"git"` sans joker ne matche *que* `git` tout seul

</div>

<div class="mt-4 rounded-lg bg-#f7e9a0 p-3 text-base">
« Merci de ne faire que de l'analyse » devient <b>incontournable</b> : même si le prompt dérive ou si le ticket pousse à « corriger vite », l'agent ne peut pas.
</div>

<style>
.slidev-layout pre { font-size: 11px !important; line-height: 16px !important; }
</style>

<!--
Syntaxe OpenCode V2. L'article montre la syntaxe V1 (permission: / bash:), même logique.
-->
