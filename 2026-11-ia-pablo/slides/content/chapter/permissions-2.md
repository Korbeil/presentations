# Read-only par construction, pas par promesse

<div class="mt-4 text-base space-y-1">

- clé = nom d'outil (`read`, `grep`, `bash`, `skill`, …) ; `"*"` = défaut pour tout le reste
- `bash` : règles par motif, **la dernière qui matche gagne** — l'ordre est tout
- motifs matchés sur la commande **parsée, arguments inclus** : `"git"` seul ne matche pas `git log`

</div>

<div class="mt-12 rounded-lg bg-#f7e9a0 p-4 text-lg">

Ces surcharges rendent « merci de ne faire que de l'analyse » <b>incontournable</b> : même si le prompt dérive ou si le ticket pousse l'agent à « corriger vite », il ne peut pas.

</div>
