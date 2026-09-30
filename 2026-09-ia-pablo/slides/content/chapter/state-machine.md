# One state machine, nine states

Graph engineering? It is a **state machine** — a table in one class.

<div class="text-xs">

| State | Entered by | What happens on entry |
| --- | --- | --- |
| <mdi-hammer class="text-[#e9ce37]"/> `in-progress` | `pablo task:start <issue-url>` | creates branch + worktree, runs `task-analyst` |
| <mdi-sleep class="text-[#e9ce37]"/> `waiting` | `pablo task:waiting` | nothing — polling stops |
| <mdi-pencil class="text-[#e9ce37]"/> `draft` | `/pablo-commit-and-pr` | commit, push, draft PR opened |
| <mdi-circle class="text-red-500"/> `ci-red` | poller: CI failing | runs `ci-analyst` on the failing checks |
| <mdi-eye class="text-[#e9ce37]"/> `ready-to-review` | poller: CI green | marks the PR ready, settles into the next state |
| <mdi-eye-outline class="text-[#e9ce37]"/> `waiting-review` | from the previous one | waits for humans |
| <mdi-flask class="text-[#e9ce37]"/> `needs-testing` | poller: approving review | records the QA baseline timestamp |
| <mdi-source-pull class="text-[#e9ce37]"/> `request-changes` | poller: changes requested | back to draft, runs `pr-feedback` |
| <mdi-bug class="text-red-500"/> `testing-failed` | poller: QA failure signal | back to draft, runs `task-feedback` |

</div>

<div class="mt-2 rounded-lg p-3 text-sm">
<b>The golden rule:</b> every arrow <b>into <code>draft</code></b> is a command I typed. Every other arrow is the poller.<br>
I decide when work leaves my hands; the machine handles the rest.
</div>

<style>
.slidev-layout table th,
.slidev-layout table td {
  padding-top: 0.15rem;
  padding-bottom: 0.15rem;
}
</style>
