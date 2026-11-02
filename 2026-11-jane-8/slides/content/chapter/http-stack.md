---
layout: split
clicks: 3
---

# Jane now runs on Symfony HttpClient

<div class="mt-2 mb-5 text-base opacity-80">One generated request in Jane 7, from top to bottom:</div>

<LayerStack />

::right::

### Why leave the PSR standards?

<div class="mt-4 text-lg font-600">We like them. In Jane's case, they cost more than they gave.</div>

<div class="mt-6 space-y-3 text-base">

<div v-click="1"><mdi-layers-triple-outline /> three abstractions over a transport most of you already used</div>
<div v-click="2"><mdi-water-outline /> PSR-7 streams to juggle for every body</div>
<div v-click="3" class="text-lg font-700"><mdi-lock-outline /> a blocking request/parse cycle: no room for deferred or concurrent calls</div>

</div>

<div v-click="3" class="mt-6 text-sm opacity-80">
PSR-7, PSR-17, PSR-18 and HTTPlug: <b>gone from the dependencies</b>.
</div>

<!--
~1 min 30. The heart of 8.0.
Click 1: the bottom layer lights up: most of you backed PSR-18 with Symfony HttpClient anyway.
Click 2: the four middle layers collapse.
Click 3: the real reason: PSR-18 is blocking by design. That is what made the next chapter impossible.
-->
