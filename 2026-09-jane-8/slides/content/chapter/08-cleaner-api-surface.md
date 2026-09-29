# A cleaner API surface

## `Result`, `FETCH_OBJECT` and the `$fetch` parameter are gone

<div class="grid grid-cols-2 gap-8 text-sm">

<div>

<v-clicks>

- `Result` wrapper (and `toObject()`, `await()`, `cancel()`) removed
- `FETCH_RESPONSE` and the legacy `$fetch = 'response'` gone
- Client methods **lost their trailing `$fetch` parameter** — they just return the model
- State introspection now uses the PHP **reflection API**
- Custom `Endpoint` implementations add `getTargetClass(): ?string`

</v-clicks>

</div>

<div>

```php
// batching: raw responses + stream()
$raw = [
    $apiClient->executeRawEndpoint(
        new ListPetsEndpoint()
    ),
    $apiClient->executeRawEndpoint(
        new ListOwnersEndpoint()
    ),
];

foreach ($apiClient->stream($raw) as $response => $chunk) {
    if ($chunk->isLast()) {
        // $response->getStatusCode() ...
    }
}
```

</div>

</div>

<div class="grid grid-cols-2 gap-8 text-xs pt-2 opacity-80">

<v-clicks>

```php
$endpoint->getTargetClass(); // 'Pet' or null
```

```php
GhostFactory::canCreate(); // PHP >= 8.4?
GhostFactory::create($class, $parse);
```

</v-clicks>

</div>
