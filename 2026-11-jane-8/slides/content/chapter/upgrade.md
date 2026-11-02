---
layout: split
---

# Upgrade without losing an afternoon

<div class="mt-2 text-base opacity-80">Jane 8 requires <b>PHP 8.3</b> (7.x accepted 8.1). Go in two steps:</div>

<div class="mt-5 space-y-4">

<div class="step">
<div class="n">1</div>
<div>
<div class="font-600">Keep the 7.x runtime behaviour</div>

```php
'default-fetch-mode' => 'eager',
'throw-unexpected-status-code' => false,
```

</div>
</div>

<div class="step" v-click>
<div class="n">2</div>
<div>
<div class="font-600">Bump, regenerate, fix the calling code until tests are green</div>
</div>
</div>

<div class="step" v-click>
<div class="n">3</div>
<div>
<div class="font-600">Remove the two lines, <b>one at a time</b></div>
<div class="text-sm opacity-70">and enjoy lazy calls and strict status codes</div>
</div>
</div>

</div>

::right::

### Or let an agent do it

<div class="mt-3 text-base">Jane ships <b>agent skills</b>: Claude Code, OpenCode, Codex, Cursor…</div>

<pre class="term mt-4"><span class="y">$</span> npx skills add janephp/janephp \
    --skill jane-upgrade</pre>

<div class="mt-5 space-y-2 text-sm">

<v-clicks at="3">

- bumps every `jane-php/*` package together
- regenerates, rewrites getters &amp; setters
- migrates HTTPlug plugins to decorators
- greps for leftovers at the end

</v-clicks>

</div>

<div v-click="7" class="mt-4 text-sm opacity-80">
Starting fresh? <code>jane-openapi-sdk</code> &amp; <code>jane-json-schema-models</code>
</div>

<style>
.step { display: grid; grid-template-columns: 2.2rem 1fr; gap: 0.8rem; align-items: start; }
.step .n { width: 2.2rem; height: 2.2rem; border-radius: 50%; background: var(--ink); color: var(--jaune); display: flex; align-items: center; justify-content: center; font-weight: 700; }
.step pre { margin-top: 0.4rem; font-size: 12px !important; }
</style>

<!--
~1 min 15. Same advice by hand or with an agent: two steps.
Full guide in the compatibility documentation.
-->
