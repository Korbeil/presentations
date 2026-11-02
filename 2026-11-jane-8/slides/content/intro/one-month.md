---
layout: punchline
clicks: 3
---

<div class="timeline">
  <div class="step" :class="{ on: $clicks >= 1 }">
    <div class="date">Sep 1st</div>
    <div class="ver">7.14</div>
    <div class="what">still Jane 7</div>
  </div>
  <div class="line" :class="{ on: $clicks >= 2 }" />
  <div class="step" :class="{ on: $clicks >= 2 }">
    <div class="date">Oct 1st</div>
    <div class="ver accent">8.0</div>
    <div class="what">breaking changes, chosen one by one</div>
  </div>
  <div class="line" :class="{ on: $clicks >= 3 }" />
  <div class="step" :class="{ on: $clicks >= 3 }">
    <div class="date">Oct 23rd</div>
    <div class="ver teal">8.1</div>
    <div class="what">pagination, finally</div>
  </div>
</div>

<div class="mt-14 text-2xl opacity-80 leading-relaxed">
A major version of a code generator changes the code it writes,<br>
and therefore <span class="accent">the code you write</span>.
</div>

<style>
.timeline {
  display: flex;
  align-items: center;
  gap: 1.5rem;
}
.timeline .step {
  opacity: 0.12;
  transform: translateY(0.8rem);
  transition: all 0.5s cubic-bezier(0.2, 0.8, 0.2, 1);
}
.timeline .step.on {
  opacity: 1;
  transform: none;
}
.timeline .date {
  font-size: 0.85rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  opacity: 0.6;
}
.timeline .ver {
  font-size: 4.5rem;
  font-weight: 700;
  line-height: 1;
}
.timeline .what {
  font-size: 0.95rem;
  opacity: 0.7;
  max-width: 12rem;
}
.timeline .line {
  flex: 1;
  height: 4px;
  border-radius: 2px;
  background: linear-gradient(90deg, var(--jaune), var(--jane));
  transform: scaleX(0);
  transform-origin: left;
  transition: transform 0.6s cubic-bezier(0.2, 0.8, 0.2, 1);
}
.timeline .line.on {
  transform: scaleX(1);
}
</style>

<!--
~40 s. Exactly one month between the last 7.x and 8.0. Then 23 days for 8.1.
Jane generated PSR-18 clients and getter/setter models for years, and they worked.
They also stacked layers, hid the shape of your data, and made some features impossible. Jane 8 removes those layers.
-->
