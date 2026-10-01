# Un couplage, une interface

PABLO ne sait de l'ADE que ce qui tient derrière une interface :

```php
interface AgentLauncherInterface
{
    public function launch(
        string $worktree,
        Agent $agent,
        string $prompt,
        string $project,
        string $branch,
    ): string;
}
```

<div class="mt-4 text-base space-y-1">

- **lancer un agent + être prévenu de la fin du run** — c'est tout ce que PABLO demande à l'ADE
- le swap a déjà eu lieu une fois : <b>Orca → OpenChamber</b>, une seule classe réécrite
- un seul couplage résiste : quand l'ADE refuse un worktree, la sortie de secours est un headless <code>opencode run</code> — ce couplage-là, je l'assume

</div>

<div class="mt-8 rounded-lg bg-#f7e9a0 p-3 text-base">
<b>La vérité fut toujours dans les agents.</b> Ce qui manquait : quelque chose d'assez bête pour tourner toutes les cinq minutes pour toujours, sans s'ennuyer.
</div>
