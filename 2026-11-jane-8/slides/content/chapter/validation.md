# Your schema is validated first

<div class="mt-2 text-base opacity-80">
A generator fails worst when it crashes halfway: a raw <code>TypeError</code> in a denormalizer, and no clue which line of your spec caused it.
</div>

<div class="mt-6 grid grid-cols-[1.35fr_1fr] gap-8 items-start">

<div>

<div class="text-sm font-600 opacity-70 mb-2"><code>x-fetch-mode</code> on a POST:</div>

<pre class="term"><div class="dots"><i></i><i></i><i></i></div><span class="y">$</span> vendor/bin/jane-openapi generate

<span class="err">Unsupported feature(s) found in your schema:</span>
`x-fetch-mode` is only supported on GET and HEAD
operations but was found on a post operation at
<span class="y">"/paths/~1pets/post/x-fetch-mode"</span>.
<span class="ok">Other verbs are always executed eagerly:
remove the attribute.</span></pre>

</div>

<div class="space-y-4 text-base">

<v-clicks>

- <mdi-shield-check-outline class="text-[#e9ce37]"/> runs **before** any guessing or generation
- <mdi-format-list-checks class="text-[#e9ce37]"/> collects **every** problem in one run
- <mdi-map-marker-outline class="text-[#e9ce37]"/> an exact **JSON pointer** and a **fix hint** for each
- <mdi-cog-outline class="text-[#e9ce37]"/> config too: `--config-file` and the Symfony bundles reject **unknown keys**

</v-clicks>

</div>

</div>

<div v-click class="mt-6 callout text-lg">
A typo in an option used to cost a debugging session. Now it costs one error message.
</div>

<!--
~1 min 15. The validation pass arrived during 7.x; Jane 8 makes it the entry gate of every new feature.
-->
