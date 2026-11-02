---
layout: split
---

# What does a lazy call return?

<div class="mt-1 mb-4 text-base opacity-80">The response does not exist yet…</div>

```php {1|3-5|6|all}
$pet = $client->getPet('pet-1'); // nothing sent yet

if ($showDetails) {
    echo $pet->name; // sent and parsed here
}
// $showDetails false? no request, ever.

$pet instanceof Pet; // true
```

<div v-click="3" class="mt-6 callout text-lg">
Not a wrapper, not a promise: <b>your model</b>.
</div>

::right::

### A lazy ghost

<div class="mt-3 text-lg">
A real instance of the generated class, built with <b>PHP 8.4 native lazy objects</b>.
</div>

<div class="mt-6 space-y-3 text-base">

<div v-click="1"><mdi-check-bold /> passes <code>instanceof</code>, can be cloned &amp; serialized</div>
<div v-click="1"><mdi-gesture-tap /> the <b>first property read</b> triggers the request</div>
<div v-click="2"><mdi-swap-horizontal /> runs the endpoint's own <b>status code mapping</b>, then fills the object</div>

</div>

<style>
.slidev-layout pre { font-size: 14px !important; line-height: 22px !important; }
</style>

<!--
~1 min. Line highlights walk through the code.
ReflectionClass::newLazyGhost(): no proxy library, no generated proxy class. The object is the model.
-->
