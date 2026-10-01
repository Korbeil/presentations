# Lazy ghost proxies

<div class="grid grid-cols-2 gap-6 text-sm">

<div>

```php
$pet = $apiClient->getPet('pet-1'); // x-fetch-mode: lazy

// nothing has been sent yet:
$pet->name; // sends the request, parses the
            // response — then returns "Rex"

// and it is the model itself, not a wrapper:
$pet instanceof Pet;   // true
clone $pet;            // like a plain model
serialize($pet);       // works too

$reflector = new \ReflectionClass($pet::class);
$reflector->isUninitializedLazyObject($pet);
$reflector->initializeLazyObject($pet);
```

</div>

<div>

<v-click>

### How it works

`ReflectionClass::newLazyGhost()` — PHP **8.4 native lazy objects**
([PR #1089](https://github.com/janephp/janephp/pull/1089))

- Initializer runs the endpoint's own status mapping: **4xx/5xx throw on first access**
- Dropping an unconsumed proxy cancels the transfer (GC = drop-to-cancel)

</v-click>

<v-click>

### Graceful degradation

Not a single-model response — arrays, maps, scalars, 204… — or PHP < 8.4 (`GhostFactory::canCreate()` = **PHP ≥ 8.4**: `symfony/var-exporter` & `proxy-manager-lts` considered but rejected): **deferred modes fall back to eager**

</v-click>

</div>

</div>
