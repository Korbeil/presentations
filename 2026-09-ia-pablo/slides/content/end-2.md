# PABLO is public

<div class="mt-4 text-xl">

<mdi-github class="text-[#e9ce37]"/> **PABLO is public** — <https://github.com/korbeil/pablo>

</div>

<div class="mt-4 text-sm opacity-70 space-y-1">

- PHP 8.4+
- `./bin/install.sh`
- `pablo system:doctor`

</div>

<div class="mt-8 text-lg">Day to day:</div>

```bash {lines:false}
pablo task:start https://acme.atlassian.net/browse/XXX-123           # start a task from an issue
pablo task:start --project wallet-kit "fix callback verification"    # …or from a prompt
pablo task:list            # see all active tasks and their state
/pablo-commit-and-pr       # commit, push, open a draft PR
pablo task:waiting         # pause/resume a task
pablo task:close [branch]  # abandon/clean up a task
```
