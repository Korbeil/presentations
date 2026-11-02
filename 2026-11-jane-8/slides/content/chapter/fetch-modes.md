---
clicks: 4
---

# `x-fetch-mode`: three ways to run a GET

<div class="mt-6">
<FetchModes />
</div>

<div class="mt-6 grid grid-cols-[1fr_1.3fr] gap-8 items-center" v-click="4">

```yaml
/pets/{id}:
  get:
    operationId: getPet
    x-fetch-mode: preload
```

<div class="text-base space-y-2">

- per operation, or for all with the **`default-fetch-mode`** option
- **GET & HEAD only**: a lazy POST that nobody reads would never run

</div>

</div>

<style>
.slidev-layout pre { font-size: 12px !important; line-height: 17px !important; }
</style>

<!--
~1 min 30. The feature we had wanted for the longest time, unlocked by leaving PSR-18.
Click 1 eager: the historical behaviour, your code waits (hatched bar).
Click 2 lazy, the new default: the bar only starts when you read $pet->name. If you never read it, nothing is ever sent.
Click 3 preload: sent right away, without waiting: several of them run concurrently.
Click 4: how to pick it.
-->
