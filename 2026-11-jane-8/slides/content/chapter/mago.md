---
clicks: 3
---

# How do you know a generator writes correct code?

<div class="mt-2 text-base opacity-80">
Fixtures prove the output did not change by accident. Not that it is <b>correct</b>.
</div>

<div class="mt-8 text-sm opacity-70">Static analysis of the whole suite: <b>183 fixtures, ~20,200 generated files</b></div>

<div class="race mt-3">
  <div class="row" :class="{ on: $clicks >= 1 }">
    <span class="who">PHPStan</span>
    <span class="track"><span class="bar slow" /></span>
    <span class="time">638 s <small>· 5 processes, to avoid OOM</small></span>
  </div>
  <div class="row" :class="{ on: $clicks >= 2 }">
    <span class="who">Mago</span>
    <span class="track"><span class="bar fast" /></span>
    <span class="time">2 s</span>
  </div>
</div>

<div class="mt-10 grid grid-cols-[auto_1fr] gap-10 items-end" v-click="3">

<div class="stat">
<div class="bignum">2,000<small>+</small></div>
<div class="cap">missing <code>return</code> statements in generated code</div>
</div>

<div class="text-lg pb-2">
…found by running Mago on <b>what Jane writes</b>. All fixed in 8.0.
</div>

</div>

<style>
.race { display: flex; flex-direction: column; gap: 0.8rem; }
.race .row { display: grid; grid-template-columns: 6rem 1fr 15rem; align-items: center; gap: 1rem; opacity: 0.15; transition: opacity 0.4s; }
.race .row.on { opacity: 1; }
.race .who { font-weight: 700; font-size: 1.2rem; }
.race .track { height: 1.6rem; background: #f5f5f3; border-radius: 0.4rem; overflow: hidden; }
.race .bar { display: block; height: 100%; width: 0; border-radius: 0.4rem; }
.race .bar.slow { background: #d6d6d3; transition: width 3s linear; }
.race .bar.fast { background: var(--jane); transition: width 0.25s ease-out; }
.race .row.on .bar.slow { width: 100%; }
.race .row.on .bar.fast { width: 0.6%; min-width: 6px; }
.race .time { font-family: 'JetBrains Mono NL', monospace; font-weight: 600; }
.race .time small { font-family: 'Josefin Sans', sans-serif; font-weight: 400; opacity: 0.6; }
</style>

<!--
~1 min. Click 1: let the PHPStan bar crawl (3 s of animation for 638 s of real life).
Click 2: Mago is a sliver. Click 3: what it found.
-->
