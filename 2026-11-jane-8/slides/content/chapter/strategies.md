# Real APIs disagree: four strategies

<div class="mt-6 grid grid-cols-4 gap-4">

<div class="card" v-click>
<div class="name"><mdi-cursor-default-click-outline /> cursor</div>
<div class="how"><code>?cursor=</code> read from <code>meta.nextCursor</code>, stops when empty</div>
</div>

<div class="card" v-click>
<div class="name"><mdi-numeric /> page</div>
<div class="how"><code>?page=</code> incremented from the spec default, stops on an empty page</div>
</div>

<div class="card" v-click>
<div class="name"><mdi-link-variant /> link-header</div>
<div class="how">RFC 8288 <code>Link: &lt;…&gt;; rel="next"</code>, the GitHub way</div>
</div>

<div class="card" v-click>
<div class="name"><mdi-arrow-right-bold-box-outline /> next-link</div>
<div class="how">a next URL in the body, like OData's <code>@odata.nextLink</code></div>
</div>

</div>

<div class="mt-6" v-click>

```php
'pagination' => [
    ['^/items$', 'GET', ['strategy' => 'cursor', 'param' => 'cursor', 'next-cursor' => 'meta.nextCursor', 'items' => 'data']],
    ['^/repos$', 'GET', ['strategy' => 'page', 'param' => 'page']],
    ['^/repos/\{owner\}/issues$', 'GET', ['strategy' => 'link-header']],
    ['^/users$', 'GET', ['strategy' => 'next-link', 'next' => '@odata.nextLink', 'items' => 'value']],
],
```

</div>

<div class="mt-4 text-base" v-click>
<mdi-shield-check-outline class="text-[#e9ce37]"/> And yes: this config goes through <b>the same validation</b> as your schema. A typo, or a path missing from the response model, stops the generation.
</div>

<style>
.card { background: #f5f5f3; border-radius: 0.7rem; padding: 0.9rem; border-top: 4px solid var(--jane); }
.card .name { font-size: 1.15rem; font-weight: 700; display: flex; align-items: center; gap: 0.4rem; }
.card .how { margin-top: 0.4rem; font-size: 0.8rem; line-height: 1.35; opacity: 0.8; }
.slidev-layout pre { font-size: 10.5px !important; line-height: 16px !important; }
</style>

<!--
~1 min. Other options in the docs: yielding whole pages, capping the number of requests.
8.1 also brings enum improvements and fixes: see the changelog.
-->
