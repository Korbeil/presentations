# PABLO est public

<div class="mt-4 text-xl">

<mdi-github class="text-[#e9ce37]"/> **PABLO est public** — <https://github.com/korbeil/pablo>

</div>

<div class="mt-4 text-sm opacity-70 space-y-1">

- PHP 8.4+
- `./bin/install.sh` — dépendances, liens agents/commands, scheduler, `pablo system:doctor`
- un seul utilisateur : moi. À lire, emprunter, *casser* — pas un framework

</div>

<div class="mt-8 text-lg">Une journée complète :</div>

```bash {lines:false}
pablo task:start https://acme.atlassian.net/browse/XXX-123   # je prends un ticket
# ... je travaille avec l'agent
/pablo-commit-and-pr                                          # commit, push, draft PR
# ... et on arrête d'y penser : le poller prend le relais
```

<div class="mt-4 text-base opacity-80">
PABLO n'a rien d'intelligent : il regarde des PRs, lit des timestamps, compare à il y a dix minutes, conclut que quelque chose a changé. <b>Et il ne s'ennuie jamais.</b>
</div>
