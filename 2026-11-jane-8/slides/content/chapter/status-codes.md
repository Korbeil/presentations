# Undeclared status codes throw

<div class="mt-2 text-base opacity-80">
The API answers a status code (or content type) your spec does not declare.
</div>

<div class="mt-8 grid grid-cols-2 gap-10">

<div>

<div class="chip mb-3">Jane 7</div>

```php
$pet = $client->getPet('pet-1'); // 418? → null

// … three function calls later
$this->notify($pet->name);
// Error: Attempt to read property "name" on null
```

</div>

<div v-click>

<div class="chip teal mb-3">Jane 8</div>

```php
$pet = $client->getPet('pet-1');
// throws BadResponseException, response attached
```

<div class="mt-4 text-base">
An exception <b>at the boundary</b>, carrying the response: easy to debug.
</div>

</div>

</div>

<div class="mt-8" v-click>
<div class="text-lg"><code>throw-unexpected-status-code</code> is now <b>on by default</b></div>
<div class="mt-3 flex flex-wrap items-center gap-3 text-base">
<span class="chip">announced in #377</span>
<span class="chip">asked again in #815</span>
<span class="opacity-60">set it to <code>false</code> for the old behaviour</span>
</div>
</div>

<style>
.slidev-layout pre { font-size: 13px !important; line-height: 20px !important; }
</style>

<!--
~1 min. A null that should have been a Pet explodes far from its cause.
-->
