# Read-only par construction, pas par promesse

OpenCode résout chaque appel d'outil en trois verdicts : `allow`, `ask`, `deny`.

```yaml
---
description: Analyser un ticket Jira et produire un plan d'action
mode: subagent
permission:
  edit: deny        # edit/write/patch/multiedit derrière une seule clé
  webfetch: deny
  bash:
    "*": deny           # par défaut : rien ne s'exécute
    "git *": allow      # ... sauf git
    "git push *": deny  # ... mais jamais de push
---
```

<div class="mt-4 text-base space-y-1">

- clé = nom d'outil (`read`, `grep`, `bash`, `skill`, …) ; `"*"` = défaut pour tout le reste
- `bash` : règles par motif, **la dernière qui matche gagne** — l'ordre est tout
- motifs matchés sur la commande **parsée, arguments inclus** : `"git"` seul ne matche pas `git log`

</div>

<div class="mt-6 rounded-lg bg-#f7e9a0 p-3 text-base">
Ces surcharges rendent « merci de ne faire que de l'analyse » <b>incontournable</b> : même si le prompt dérive ou si le ticket pousse l'agent à « corriger vite », il ne peut pas.
</div>
