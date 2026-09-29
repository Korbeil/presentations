---
layout: statement
---

# `x-fetch-mode`

## A per-operation fetch strategy for **GET & HEAD** — pick how (and when) the request runs

<div class="grid grid-cols-3 gap-6 pt-6 text-sm">

<v-clicks>

<div>

### <mdi-sleep class="text-blue-500" /> lazy

**Default.** Nothing is sent when the method is called. Request + parse happen on first access.

</div>

<div>

### <mdi-clock-fast class="text-orange-500" /> eager

Historical behavior: blocking request, parsed and exceptions thrown at call time.

</div>

<div>

### <mdi-ray-start-arrow class="text-green-500" /> preload

Request registered immediately, progresses concurrently with other in-flight calls. Parsed on first access.

</div>

</v-clicks>

</div>

<div class="pt-6 text-center text-sm opacity-70">

Mutating verbs (POST, PUT, PATCH…) are **always eager** — misuse fails generation with a clean error

</div>

<div class="pt-2 text-center text-xs opacity-60">

Resolution precedence: `x-fetch-mode` → `default-fetch-mode` option → `lazy`

</div>
