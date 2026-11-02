---
layout: split
---

# The nightly corpus job

<div class="mt-2 text-base opacity-80">Twelve real-world specs, published by their vendors. Every night.</div>

<div class="mt-6 flex flex-wrap gap-2">
<span class="chip"><mdi-kubernetes /> Kubernetes</span>
<span class="chip"><mdi-docker /> Docker</span>
<span class="chip"><mdi-slack /> Slack</span>
<span class="chip">Netlify</span>
<span class="chip"><mdi-github /> GitHub 3.0</span>
<span class="chip"><mdi-github /> GitHub 3.1</span>
<span class="chip">Stripe</span>
<span class="chip">Plaid</span>
<span class="chip">Box</span>
<span class="chip">Twilio</span>
<span class="chip">Discord</span>
<span class="chip">OpenAI</span>
</div>

<div class="mt-8 space-y-2 text-base">

<v-clicks>

- <mdi-check-circle-outline class="text-[#4cd1c5]"/> generation **does not crash**
- <mdi-check-circle-outline class="text-[#4cd1c5]"/> the output **parses**
- <mdi-check-circle-outline class="text-[#4cd1c5]"/> since 8.1: **zero Mago findings** on the whole corpus

</v-clicks>

</div>

::right::

### It paid for itself before the release

<div class="mt-6 space-y-6">

<div class="stat" v-click>
<div class="bignum">Slack</div>
<div class="cap">fatal error on the public Swagger 2.0 spec</div>
</div>

<div class="stat" v-click>
<div class="bignum">OpenAI</div>
<div class="cap">fatal error on the 3.1 spec</div>
</div>

<div v-click class="text-lg font-700">Both fixed in 8.0.0, before you ever hit them.</div>

</div>

<!--
~45 s.
-->
