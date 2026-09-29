# Designing it taught me a few things

<div class="grid grid-cols-2 gap-8 mt-2 text-base">

<div>

- **Choosing what is *not* an event.** CI pending triggers nothing; CI red in `needs-testing` triggers nothing.
- **Exactly one way back into `draft`**: an explicit command, never a raw `git push`. A command is a signal — a push is noise.
- **Reviews, defined:** mine excluded, bots ignored unless whitelisted, latest review per reviewer wins, a non-approval beats every approval.
- **Not everything deserves an LLM:** two LLM-powered prompts became plain PHP (`pablo show:prs` reads the poller's cache). The intelligence is in five markdown files; the rest is plumbing.

</div>

<div>

**A green CI is a policy, not a fact**

```yaml
ci:
  ignore_checks: ["approval"]
```

<div class="mt-2 opacity-80">CircleCI publishes manual deployment gates as checks: they would hold "green" forever.</div>

<div class="mt-4 rounded-lg bg-#f7e9a0 p-3">
**The one exception:** `rebase-conflict-resolver` — the only agent allowed to write (`edit`, `write`, `git push`). Dry-run by default, pushes with `--force-with-lease`, prints `PABLO_CONFLICT_UNRESOLVABLE` when it should not touch anything. It may rewrite my branch, never merge, approve or comment as me.
</div>

</div>

</div>

<div class="mt-3 text-base opacity-80">
"The dangerous permission was never `edit`; it was acting as me in front of other people."
</div>
