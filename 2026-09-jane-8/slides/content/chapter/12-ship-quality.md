# Ship quality

<div class="grid grid-cols-2 gap-8 text-sm mt-2">

<div>

<mdi-test-tube class="text-red-500" /> **Corpus smoke job**

<v-clicks>

Nightly, non-blocking CI run: generate a client per **real vendor spec**, pinned in `corpus/specs.json`

<span class="text-[11px] opacity-70">Kubernetes · Docker · Slack · Netlify · GitHub 3.0/3.1 · Stripe · Plaid · Box · Twilio · Discord · OpenAI</span>

Generation must not crash, output must parse; Mago runs report-only.

</v-clicks>

</div>

<div>

<mdi-magnify-scan class="text-purple-500" /> **Static analysis of generated code**

<v-clicks>

- Generated output analysed with **Mago** (pinned version, [ADR 0011](https://github.com/janephp/janephp/blob/next/docs/contributing/adrs/0011-static-analysis-of-generated-code.md))
- Baselines tracked — regressions surface in review
- PhpParser syntax gate shared by fixture tests

</v-clicks>

</div>

</div>

<v-clicks>

```text
$ php vendor/bin/jane-openapi generate
 Generating for schema `open-api.json`
 Output: `generated/`
 ➜ Guessing… done (0.05s)
 ➜ Generating… done (0.30s)
 ➜ 23 files written
     • 5 Models   • 6 Normalizers   • 10 Runtime
     • 1 Client   • 1 Endpoints
 [OK] Done in 0.35s
```

</v-clicks>
