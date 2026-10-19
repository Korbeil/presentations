# L'exception à mon propre dogme

Toutes les 12 h, le sync rebase chaque worktree sur la branche primaire. En cas de conflit, git abandonne, et un agent refait le rebase.

`rebase-conflict-resolver` — le seul agent **autorisé à écrire** :

```yaml {lines:false}
permissions:
  - { action: edit,  resource: "*",              effect: allow }
  - { action: shell, resource: "*",              effect: allow }
  - { action: shell, resource: "gh pr merge*",   effect: deny }  # il peut réécrire ma branche...
  - { action: shell, resource: "gh pr review*",  effect: deny }  # ...pas agir en mon nom
  - { action: shell, resource: "gh pr comment*", effect: deny }
  # ... + gh pr edit/ready/close, gh issue *, acli jira workitem *
```

<div class="mt-4 text-base space-y-1.5">

- dry-run par défaut ; `auto_apply: true` <b>seulement</b> là où je connais la forme du travail
- jamais `--force` : `--force-with-lease` — si j'ai poussé entre-temps, le job recule, mon push gagne toujours
- branche sale : jamais rebasée ; conflit qui demande un humain → `PABLO_CONFLICT_UNRESOLVABLE`, rien n'est poussé
- et toutes les heures, le checkout principal est remis sur `origin/main` (`checkout` + `reset --hard`) — seulement s'il est propre et sans commit en avance ; sinon, PABLO n'y touche pas

</div>

<!--
Mise à jour du checkout principal : sans agent, du code déterministe. Cadence main_update.interval_minutes (60 par défaut), désactivable par projet avec main_update.enabled: false, ou à la main avec `pablo sync:main`.
Ignoré aussi si un rebase/merge est en cours, ou si main est checkout dans un autre worktree. Les worktrees de tâche partent de origin/main, jamais du main local.
-->

<style>
.slidev-layout pre { font-size: 11px !important; line-height: 16px !important; }
</style>
