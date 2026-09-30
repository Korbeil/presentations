# What is Jane?

## Generate Models & API Clients from JSON Schema / OpenAPI specs

<div class="grid grid-cols-2 gap-8 mt-6">

<div>

<v-clicks>

- Feed Jane a **specification file**, get typed PHP code
- **OpenAPI**: full HTTP clients — endpoints, models, normalizers, authentication
- **JSON Schema**: DTOs, hydrators & Symfony validation
- Not a runtime library — this is **generated code you own**

</v-clicks>

</div>

<div>

```yaml
openapi: 3.1.0
info:
  title: Petstore
  version: 1.0.0
paths:
  /pets/{id}:
    get:
      operationId: showPetById
      responses:
        '200':
          description: A pet
```

</div>

</div>

---

# The support matrix

<div class="grid grid-cols-3 gap-6 pt-8 text-center text-sm">

<div>

### <mdi-code-braces class="text-blue-500" />

**OpenAPI**

2.0 · 3.0.x · 3.1.x

</div>

<div>

### <mdi-json class="text-orange-500" />

**JSON Schema generation**

draft 2019-09 · draft 2020-12

</div>

<div>

### <mdi-check-decagram class="text-green-500" />

**JSON Schema validation**

draft 2020-12

</div>

</div>

<div class="pt-6 text-center text-xs text-gray-800">

Full coverage in the [compatibility guide](https://jane.jolicode.com/guides/compatibility)

</div>

