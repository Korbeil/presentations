# A green CI is a policy, not a fact

```yaml {lines:false}
ci:
  ignore_checks: ["approval"]
```

<div class="mt-2 text-base opacity-80">CircleCI publishes manual deployment gates as checks: they would hold "green" forever.</div>

<div class="mt-6 text-base rounded-lg bg-#f7e9a0 p-4">
<b>The one exception:</b> <code>rebase-conflict-resolver</code> — the only agent allowed to write (<code>edit</code>, <code>write</code>, <code>git push</code>). Dry-run by default, pushes with <code>--force-with-lease</code>, prints <code>PABLO_CONFLICT_UNRESOLVABLE</code> when it should not touch anything. It may rewrite my branch, never merge, approve or comment as me.
</div>

<div class="mt-10 text-lg opacity-80">
"The dangerous permission was never <code>edit</code>; it was acting as me in front of other people."
</div>
