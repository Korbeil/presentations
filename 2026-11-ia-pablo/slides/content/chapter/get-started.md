# Installer et utiliser PABLO

<div class="mt-6 grid grid-cols-2 gap-8">

<div>

### Installer

```bash
curl -fsSL https://getpablo.dev/installer | bash
pablo system:doctor   # installé et authentifié ?
pablo project:new     # ajouter un projet
```

<div class="text-base opacity-80 space-y-1">

- **pas de PHP** : `git`, `curl`, `gh`, et `acli` / `linear` selon le tracker
- un runtime : OpenCode, Claude Code ou Copilot CLI
- un ADE : Orca, OpenChamber ou headless

</div>

</div>

<div>

### Au quotidien

```bash
pablo task:start <issue>  # worktree + analyse
/pablo-commit-and-pr      # commit, push, draft PR
pablo task:waiting        # pause / reprise
pablo task:close          # on range
```

<div class="text-base opacity-80 space-y-1">

- le reste, c'est le **poller** qui s'en charge
- `pablo list` pour voir toutes les commandes

</div>

</div>

</div>

<div class="mt-6 rounded-lg bg-#2b2b2a text-white px-5 py-3 text-base flex items-center gap-4">
<mdi-party-popper class="text-[#e9ce37] text-3xl shrink-0"/>
<div>
<b class="text-[#e9ce37]">Un seul binaire, zéro PHP.</b> Plus de clone ni de Composer : un fichier de ~29 Mo qui embarque son propre PHP, dashboard compris. Linux et macOS, x86 et ARM.
</div>
</div>

<div class="mt-4 text-center text-base opacity-80">
<a href="https://getpablo.dev">getpablo.dev</a> — quickstart et doc complète
</div>

<style>
.slidev-layout pre { font-size: 12px !important; line-height: 18px !important; }
</style>

<!--
Slide tranquille, pas de démo live : les gens veulent savoir comment s'y mettre.
Laisser le temps de prendre en photo / noter les commandes.
Le binaire : la vraie barrière à l'adoption, ce n'était pas PABLO, c'était « installe d'abord PHP 8.4 ». Je continue d'écrire du PHP, mais plus personne n'a besoin de le savoir pour l'utiliser.
Comment : Box emballe l'app en phar, collée à un micro.sfx de static-php-cli ; un php CLI statique est aussi embarqué pour servir le dashboard (pablo web).
Une release = les 7 premiers caractères du SHA ; les 4 binaires sont construits, smoke-testés (debian:stable-slim sans PHP) et vérifiés par sha256sums.txt. pablo update --rollback revient à la version précédente.
Piège rencontré : OPcache désactivé dans le binaire, opcache.enable_cli=1 plante au démarrage avec le micro de PHP 8.5.
-->
