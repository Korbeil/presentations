# Un couplage, une interface

PABLO ne sait de l'ADE que ce qui tient derrière une interface :

```php
interface AgentLauncherInterface // extrait
{
    public function launch(string $worktree, Agent $agent, string $prompt,
                           string $project, string $branch): string;
    // ... + runStartupScript(), activeSessions(), ...
}
```

<div class="mt-4 text-base space-y-1">

- **lancer un agent dans un worktree, savoir quand le run est fini** : c'est l'essentiel de ce que PABLO attend d'un ADE
- le swap a déjà eu lieu : <b>Orca → OpenChamber</b>, un adaptateur réécrit
- un couplage résiste : quand l'ADE refuse un worktree, la sortie de secours est un <code>opencode run</code> headless — celui-là, je l'assume

</div>

<div class="mt-6 text-lg">
<b>L'intelligence a toujours été dans les agents.</b> Il manquait quelque chose d'assez bête pour tourner toutes les cinq minutes, pour toujours, sans s'ennuyer.
</div>

<style>
.slidev-layout pre { font-size: 11px !important; line-height: 16px !important; }
</style>
