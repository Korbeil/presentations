# The big one: goodbye PSR-7 / HTTPlug

<div class="grid grid-cols-2 gap-8 mt-4 text-sm">

<div>

<div v-click>

### Before (7.x)

- PSR-18 client + PSR-7 messages
- PSR-17 factories to wire `Client::create()`
- HTTPlug `PluginClient` + plugins
- `nyholm/psr7` & friends in your dependency tree
- Request/response juggling in userland

</div>

</div>

<div>

<div v-click>

### After (8.x)

- `Symfony\Contracts\HttpClient\HttpClientInterface`
- Native `string|resource|array` bodies
- Plain `HttpClientInterface` decorators
- Runtime requires `symfony/http-client ^6.4 || ^7 || ^8`
- Zero `psr/*` / `php-http/*` dependencies left

</div>

</div>

</div>

<div v-click>

## [ADR 0012](https://github.com/janephp/janephp/blob/next/docs/contributing/adrs/0012-symfony-httpclient-migration-x-fetch-mode.md) — the decision record

<div class="text-sm pt-2 text-center bg-blue-500/10 rounded p-3 mt-16">

One transport abstraction instead of three — and it finally unlocks **per-operation fetch strategies**

</div>

</div>
