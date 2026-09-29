# One state machine, nine states

Graph engineering? It is a **state machine** — a table in one class.

<div class="text-xs">

| State | Entered by | What happens on entry |
| --- | --- | --- |
| 🔨 `in-progress` | `pablo task:start <issue-url>` | creates branch + worktree, runs `task-analyst` |
| 🥱 `waiting` | `pablo task:waiting` | nothing — polling stops |
| 📝 `draft` | `/pablo-commit-and-pr` | commit, push, draft PR opened |
| 🔴 `ci-red` | poller: CI failing | runs `ci-analyst` on the failing checks |
| 👀 `ready-to-review` | poller: CI green | marks the PR ready, settles into the next state |
| 👀 `waiting-review` | reached from the previous one | waits for humans |
| 🧪 `needs-testing` | poller: approving review | records the QA baseline timestamp |
| 🔁 `request-changes` | poller: changes requested | back to draft, runs `pr-feedback` |
| 🚨 `testing-failed` | poller: QA failure signal | back to draft, runs `task-feedback` |

</div>

<div class="mt-3 rounded-lg bg-#2b2b2a text-white p-3 text-base">
**The golden rule:** every arrow **into `draft`** is a command I typed. Every other arrow is the poller.<br>
I decide when work leaves my hands; the machine handles the rest.
</div>
