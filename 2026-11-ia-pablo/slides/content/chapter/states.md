# Une state machine, neuf états

Pas de `todo`, et que c'est un choix : un ticket non commencé n'a aucune tâche, il apparaît juste dans la liste de ce qui m'est assigné. Un merge ferme la tâche **depuis n'importe quel état** et supprime le worktree.

<div class="text-xs">

| État | Entré par | Ce qui se passe à l'entrée |
| --- | --- | --- |
| <mdi-hammer class="text-[#e9ce37]"/> `in-progress` | `pablo task:start <issue-url>` | crée branche + worktree, lance `task-analyst` une fois (+ script de startup du projet) |
| <mdi-sleep class="text-[#e9ce37]"/> `waiting` | `pablo task:waiting` | rien — le polling s'arrête ; le retour rétablit l'état précédent |
| <mdi-pencil class="text-[#e9ce37]"/> `draft` | `/pablo-commit-and-pr` | commit, push, draft PR ouverte |
| <mdi-circle class="text-red-500"/> `ci-red` | poller : CI en échec | lance `ci-analyst` sur les checks et leurs logs |
| <mdi-eye class="text-[#e9ce37]"/> `ready-to-review` | poller : CI verte | rend la prête sur GitHub, puis retombe dans `waiting-review` |
| <mdi-eye-outline class="text-[#e9ce37]"/> `waiting-review` | l'état ci-dessus | rien — là où une tâche attend des humains |
| <mdi-flask class="text-[#e9ce37]"/> `needs-testing` | poller : review approbatrice | stocke le timestamp qui devient la baseline QA |
| <mdi-source-pull class="text-[#e9ce37]"/> `request-changes` | poller : modifications demandées | repasse la PR en draft, lance `pr-feedback` |
| <mdi-bug class="text-red-500"/> `testing-failed` | poller : signal d'échec QA | repasse la PR en draft, lance `task-feedback` |

</div>

<div class="mt-2 rounded-lg p-3 text-sm">
<b>La règle d'or :</b> chaque flèche <b>vers <code>draft</code></b> est une commande tapée. Toutes les autres flèches viennent du poller.<br>
Je décide quand une tâche me quitte ; la machine s'occupe du reste.
</div>

<style>
.slidev-layout table th,
.slidev-layout table td {
  padding-top: 0.15rem;
  padding-bottom: 0.15rem;
}
</style>
