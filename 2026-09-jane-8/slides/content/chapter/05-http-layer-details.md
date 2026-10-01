---
layout: default
---

# Inside the HTTP layer

<span class="text-xs text-base-content/60">Decorators · authentication · no-throw parity via per-method `$throw` flags</span>

<div class="grid grid-cols-2 gap-4 mt-2 text-[12px]">

<div>

**Server URL & custom decorators**

```php
// $additionalPlugins: decorator factories,
// applied left-to-right around the client
$apiClient = Acme\Generated\Client::create(null, [
    // replaces AddHostPlugin + AddPathPlugin
    new ServerUrlHttpClient($serverUrl),

    // any decorator factory works
    static fn (HttpClientInterface $c) => $c
        ->withOptions([
            'headers' => ['X-Lang' => 'fr-FR'],
        ]),
]);
```

</div>

<div>

<v-click>

**Authentication — Symfony-style**

```php
final class ApiKeyAuthentication
    implements AuthenticationPlugin
{
    // options, not a PSR-7 request rewrite
    public function decorate(
        string $method,
        string $url,
        array &$options
    ): void {
        $options['headers']['X-API-Key']
            = $this->apiKey;
    }
}
```

</v-click>

</div>

</div>

