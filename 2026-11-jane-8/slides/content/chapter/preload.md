---
layout: split
clicks: 2
---

# `preload`: pages that aggregate APIs

<div class="mt-2 mb-4 text-base opacity-80">With <code>x-fetch-mode: preload</code> on <code>getPet</code> and <code>getOwner</code>:</div>

```php
$pet = $client->getPet('pet-1');        // request starts
$owner = $client->getOwner('owner-42'); // this one too

echo $pet->name;   // waits for the pet if needed
echo $owner->name; // most likely already there
```

<div class="mt-8 text-lg">
Same code as before. <b>Only the spec changed.</b>
</div>

::right::

### Two calls, one wait

<div class="mt-6">
<PreloadRace />
</div>

<div v-click="2" class="mt-6 text-base">
Symfony HttpClient multiplexes them: you pay for <b>the slowest</b>, not the sum.
</div>

<style>
.slidev-layout pre { font-size: 13px !important; line-height: 20px !important; }
</style>

<!--
~1 min. Click 1: eager, one after the other. Click 2: preload, both in flight at once.
-->
