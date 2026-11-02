# Models are plain PHP objects now

<div class="mt-2 text-lg opacity-80">The change you will see first, in every file that touches a generated model.</div>

<div class="mt-6 grid grid-cols-[1.4fr_1fr] gap-10 items-start">

<div>

````md magic-move {lines: false}
```php
// Jane 7: protected properties + accessors
class Pet
{
    protected string $name;
    protected ?string $tag = null;

    public function getName(): string { return $this->name; }
    public function setName(string $name): self { … }
    public function getTag(): ?string { return $this->tag; }
    public function setTag(?string $tag): self { … }
}

echo $pet->getName();
$pet->setTag('good boy');
```
```php
// Jane 8: public, natively typed properties
class Pet
{
    public string $name;
    public ?string $tag = null;
}

echo $pet->name;
$pet->tag = 'good boy';
```
````

</div>

<div class="space-y-5 text-base">

<div v-click="1">

### <mdi-language-php class="text-[#e9ce37]"/> Modern PHP

Accessors that only read and write a field add nothing but lines. Property hooks (PHP 8.4) removed the last “just in case”.

</div>

<div v-click="2">

### <mdi-auto-fix class="text-[#e9ce37]"/> Free tooling

Your IDE and static analysis read the types **straight from the declarations**.

</div>

</div>

</div>

<style>
.slidev-layout pre { font-size: 12px !important; line-height: 18px !important; }
</style>

<!--
~1 min. Click 1: the magic move, watch the getters/setters vanish.
Public typed properties are how modern PHP models plain data. If one day you need logic, a property hook does it without changing the call site.
-->
