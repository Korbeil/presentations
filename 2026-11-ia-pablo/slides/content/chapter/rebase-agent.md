# L'exception à mon propre dogme

Chaque 12 h, le sync rebase chaque worktree sur la branche primaire. En cas de conflit : un agent prend le relais.

`rebase-conflict-resolver` — le seul agent **autorisé à écrire** :

```yaml {lines:false}
permission:
  edit: allow
  write: allow
  "git push*": allow
  "gh pr merge*": deny      # il peut réécrire ma branche...
  "gh pr review*": deny     # ...il ne peut pas agir en mon nom
  "gh pr comment*": deny
```

<div class="mt-4 text-base space-y-1.5">

- `auto_apply: true` <b>seulement</b> sur les projets où je connais la forme du travail ; dry-run par défaut
- jamais de `--force` : `--force-with-lease`, mon push gagne toujours
- branche sale (fichiers non commités) : jamais rebasée ; conflit irrésolvable → `PABLO_CONFLICT_UNRESOLVABLE`, rien n'est poussé

</div>

<div class="mt-6 rounded-lg bg-#f7e9a0 p-3 text-base">
<b>Honnêtement</b> : cet agent peut faire des dégâts, contrairement aux quatre autres. J'accepte le risque parce que tout atterrit dans une PR que je relis avant merge : c'est mon code. En échange, plus une seule PR en conflit depuis des mois.
</div>

<div class="mt-4 text-lg opacity-80">
« La permission dangereuse n'a jamais été <code>edit</code> ; c'était <i>agir comme moi devant d'autres gens</i>. »
</div>
