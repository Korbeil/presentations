# Démo

<div class="mt-12 text-center">

```bash
pablo task:start https://acme.atlassian.net/browse/XXX-123
```

<div class="mt-10 text-xl space-y-6 text-left opacity-90 w-3/4 mx-auto">

1. Un lien Jira : branche, worktree et premier run de `task-analyst`, d'un coup
2. Je lis le plan, puis je travaille avec `build`
3. `/pablo-commit-and-pr` → commit, push, draft PR
4. Et **on arrête d'y penser** : le poller prend le relais
5. Un œil sur le dashboard : `pablo web` → [localhost:8321](http://localhost:8321)

</div>

</div>

<div class="absolute bottom-12 left-0 right-0 text-center text-lg opacity-70">
Si le Wi-Fi lâche, la vidéo de secours est prête :-)
</div>

<style>
.slidev-layout ol { list-style: decimal !important; padding-left: 1.5rem !important; }
.slidev-layout ol li { display: list-item !important; list-style: decimal !important; }
</style>

<!--
Avant : remplacer le lien acme par un vrai ticket sandbox.
Avoir des tâches déjà en ci-red / waiting-review / needs-testing pour remplir le dashboard.
Ne pas attendre 10 min : forcer un tour avec `pablo system:poll`.
-->
