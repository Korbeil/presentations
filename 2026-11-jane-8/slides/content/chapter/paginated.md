---
layout: split
clicks: 3
---

# `<operation>Paginated()`

<div class="mt-2 text-base opacity-80">
For every matching GET, a sibling method: same arguments, returns a <code>\Generator</code> of items.
</div>

```php
foreach ($client->listItemsPaginated(['limit' => 50]) as $item) {
    // a Vendor\Api\Model\Item, whatever page it comes from

    if ($item->id === $wanted) {
        break; // no more requests
    }
}
```

<div class="mt-6 text-lg space-y-2">

- <mdi-sleep class="text-[#e9ce37]"/> lazy in the good sense: **next page only once you consumed the previous one**
- <mdi-cog-outline class="text-[#e9ce37]"/> targeted by path regex, like `whitelisted-paths`

</div>

::right::

<PaginationFlow />

<style>
.slidev-layout pre { font-size: 12.5px !important; line-height: 19px !important; }
</style>

<!--
~1 min. Click 1: page 1 arrives, items flow. Click 2: page 2. Click 3: break, pages 3 and 4 are never requested.
-->
