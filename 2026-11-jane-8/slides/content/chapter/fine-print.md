# The fine print

<div class="mt-8 grid grid-cols-3 gap-8">

<div class="stat" v-click>
<div class="bignum"><mdi-timer-sand /></div>
<div class="cap mt-3"><b>Exceptions move</b> to the first access, not the call site</div>
</div>

<div class="stat" v-click>
<div class="bignum">8.4</div>
<div class="cap mt-3">ghosts need <b>PHP 8.4</b>; on older versions, deferred modes <b>fall back to eager</b></div>
</div>

<div class="stat" v-click>
<div class="bignum">1<small>&thinsp;model</small></div>
<div class="cap mt-3">only responses mapping to <b>a single model</b> can be deferred: arrays, scalars, 204… stay eager</div>
</div>

</div>

<div class="mt-12 grid grid-cols-[1fr_1.2fr] gap-8 items-center" v-click>

<div class="text-xl font-600">Prefer the 7.x behaviour?<br>One line.</div>

```php
'default-fetch-mode' => 'eager',
```

</div>

<!--
~45 s. Be honest about the trade-offs, then reassure: one option restores eager everywhere.
Details in the "fetch modes" section of the docs.
-->
