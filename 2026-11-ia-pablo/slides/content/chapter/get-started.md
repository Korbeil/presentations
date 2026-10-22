# Installer et utiliser PABLO

<div class="mt-6 grid grid-cols-2 gap-8">

<div>

### Installer

```bash
./bin/install.sh        # composer, shim, liens agents,
                        # scheduler en arrière-plan
pablo system:doctor     # tout est installé et authentifié ?
pablo project:new       # ajouter un projet (wizard)
```

<div class="text-base opacity-80 space-y-1">

- PHP 8.4+, Composer, `gh`, `acli`
- un ADE : Orca ou OpenChamber
- `--with-web` pour garder le dashboard allumé

</div>

</div>

<div>

### Au quotidien

```bash
pablo task:start <url-jira>   # branche, worktree, analyse
/pablo-commit-and-pr          # commit, push, draft PR
pablo task:waiting            # pause / reprise
pablo task:close              # on range
```

<div class="text-base opacity-80 space-y-1">

- le reste, c'est le **poller** qui s'en charge
- `pablo list` pour voir toutes les commandes

</div>

</div>

</div>

<div class="mt-8 text-center text-lg opacity-80">
README + <code>docs/installation.md</code> dans le dépôt
</div>

<style>
.slidev-layout pre { font-size: 12px !important; line-height: 18px !important; }
</style>

<!--
Slide tranquille, pas de démo live : les gens veulent savoir comment s'y mettre.
Laisser le temps de prendre en photo / noter les commandes.
-->
