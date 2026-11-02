---
layout: split
---

# Jane in 30 seconds

<div class="mt-6 text-lg space-y-4">

<v-clicks>

- <mdi-file-document-outline class="text-[#e9ce37]"/> Feed it an **OpenAPI** or **JSON Schema** specification
- <mdi-language-php class="text-[#e9ce37]"/> Get typed PHP: **models, normalizers, endpoints, a client**
- <mdi-account-key-outline class="text-[#e9ce37]"/> Not a runtime library: **generated code you own**

</v-clicks>

</div>

<div class="mt-10 grid grid-cols-2 gap-8" v-click>

<div class="stat teal">
<div class="bignum">290<small>k</small></div>
<div class="cap">installs every month</div>
</div>

<div class="stat teal">
<div class="bignum">690<small>&thinsp;★</small></div>
<div class="cap">on GitHub, made &amp; sponsored by JoliCode</div>
</div>

</div>

::right::

<div class="text-sm font-600 opacity-70 mb-2">openapi.yaml</div>

```yaml
paths:
  /pets/{id}:
    get:
      operationId: getPet
```

<div class="text-center text-2xl my-1"><mdi-arrow-down-bold /></div>

<pre class="term"><span class="y">$</span> vendor/bin/jane-openapi generate
<span class="dim">generated/</span>
├── Client.php      <span class="dim"># getPet()</span>
├── Endpoint/GetPet.php
├── Model/Pet.php
└── Normalizer/PetNormalizer.php</pre>

<!--
~1 min. Quick recap for people who never used it.
Spec in, PHP out. The point: the generated code is yours, it lives in your repo.
That is exactly why a major version matters: it changes the code it writes, therefore the code you write.
-->
