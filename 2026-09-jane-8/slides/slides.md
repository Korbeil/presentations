---
theme: "@slidev/theme-apple-basic"
highlighter: shiki
title: JanePHP 8.x
info: |
    Jane is a set of libraries to generate Models & API Clients based on
    JSON Schema / OpenAPI specs — https://jane.jolicode.com/

    Jane 8.x: API made easier, again.

    Learn more at https://github.com/janephp/janephp
drawings:
    persist: false
transition: slide-left
mdc: true
colorSchema: light
---

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

<div class="pt-6 text-center text-xs text-gray-800">

</div>

---
src: ./content/chapter/01-what-is-jane.md
---

---
src: ./content/chapter/02-timeline.md
---

---
src: ./content/chapter/03-ecosystem-caught-up.md
---

---
src: ./content/chapter/04-symfony-httpclient.md
---

---
src: ./content/chapter/05-http-layer-details.md
---

---
src: ./content/chapter/06-x-fetch-mode.md
---

---
src: ./content/chapter/07-lazy-ghost-proxies.md
---

---
src: ./content/chapter/08-cleaner-api-surface.md
---

---
src: ./content/chapter/08b-models-public-properties.md
---

---
src: ./content/chapter/09-pre-generation-validation.md
---

---
src: ./content/chapter/10-generation-events.md
---

---
src: ./content/chapter/11-bc-breaks.md
---

---
src: ./content/chapter/12-ship-quality.md
---

---
src: ./content/end.md
---
