# BC-breaks checklist

## The main ones to review before upgrading

<div class="grid grid-cols-2 gap-8 text-sm mt-2">

<div>

### Generated clients

<v-clicks>

- PSR-7/18 + HTTPlug → **Symfony HttpClient**
- `AddHostPlugin` + `AddPathPlugin` → one `ServerUrlHttpClient`
- Auth: `authentication(Request)` → `decorate($method, $url, &$options)`
- `$fetch` param, `FETCH_OBJECT`, `Result` removed
- `create(?HttpClientInterface, decorators, normalizers, applyServerPlugins)`
- Runtime `Client` constructor now `final`

</v-clicks>

</div>

<div>

### Generated models

<v-clicks>

- **Public, natively typed properties** replace getters/setters
- `$model->getFoo()` → `$model->foo` · `setFoo($v)` → `foo = $v`
- Uninitialized until assigned — reading before denormalization throws
- `Options` frozen value object for programmatic builds
- Instance-owned `ReferenceResolver`, no global static state
- `throw-unexpected-status-code` on by default → `UnexpectedStatusCodeException`

</v-clicks>

</div>

</div>
