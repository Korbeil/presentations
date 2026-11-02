# Creating a client looks almost the same

<div class="mt-4 grid grid-cols-[1.5fr_1fr] gap-10 items-start">

<div>

````md magic-move {lines: false}
```php
// with no argument, Jane calls HttpClient::create() for you
$client = Vendor\Api\Client::create();
```
```php
use Symfony\Component\HttpClient\HttpClient;

// or bring your own client: proxy, timeout, scoped client...
$client = Vendor\Api\Client::create(
    HttpClient::create(['timeout' => 5]),
);
```
```php
use Symfony\Component\HttpClient\HttpClient;
use Symfony\Contracts\HttpClient\HttpClientInterface;

// HTTPlug plugins become decorator factories:
// any callable(HttpClientInterface): HttpClientInterface
$client = Vendor\Api\Client::create(
    HttpClient::create(['timeout' => 5]),
    [
        static fn (HttpClientInterface $httpClient): HttpClientInterface
            => $httpClient->withOptions([
                'headers' => ['Accept-Language' => 'en-GB'],
            ]),
    ],
);
```
````

</div>

<div class="space-y-5 text-base">

<div class="chip"><mdi-numeric-1-circle /> zero config</div>
<div v-click="1" class="chip"><mdi-numeric-2-circle /> your own client</div>
<div v-click="2" class="chip"><mdi-numeric-3-circle /> decorators: a closure is enough</div>

<div v-click="3" class="pt-4 space-y-3">

- **Authentication** adds a header or query param to the request **options**, no more PSR-7 rebuild
- The **server URL** of your spec is still applied for you, by a small dedicated decorator

</div>

</div>

</div>

<style>
.slidev-layout pre { font-size: 12.5px !important; line-height: 19px !important; }
.chip { display: flex; width: fit-content; }
</style>

<!--
~1 min. Three steps of the same line growing.
Nothing to install besides symfony/http-client, which you probably already have.
-->
