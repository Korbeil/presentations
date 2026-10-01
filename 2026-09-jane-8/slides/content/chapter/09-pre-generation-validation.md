# Pre-generation schema validation

<div class="grid grid-cols-2 gap-6 mt-2">

<div>

```yaml
# Valid in OpenAPI 3.1.x,
# rejected by jane-php/open-api-3:
type:
  - string
  - 'null'
```

```text
Unsupported feature(s) found in your schema:

`type` must be a string in OpenAPI 3.0.x,
array given ("string", "null")
at "/components/schemas/Pet/properties/status/type".
Type arrays are an OpenAPI 3.1 feature: generate
with jane-php/open-api-3-1 instead, or rewrite
using `nullable: true` / `oneOf`.
```

</div>

<div>

<div v-click>

### Fail fast, fail well

([ADR 0002](https://github.com/janephp/janephp/blob/next/docs/contributing/adrs/0002-pre-generation-schema-validation.md))

</div>

<v-clicks at="2">

- Generation **stops before any work** happens
- **Every** violation is reported in one run
- Exact **RFC 6901 JSON pointer** per violation
- A fix hint: which component, or how to rewrite
- No more raw `TypeError` escaping to the console

</v-clicks>

</div>

</div>
