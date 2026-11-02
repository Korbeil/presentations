<script setup lang="ts">
import { useSlideContext } from '@slidev/client'

const { $clicks } = useSlideContext()

// Timeline in percent: the method is called at CALL, the result is first read at ACCESS.
const CALL = 8
const ACCESS = 62

const lanes = [
  {
    mode: 'eager',
    icon: 'i-mdi-clock-fast',
    tag: 'the 7.x behaviour',
    bar: { from: CALL, to: CALL + 30 },
    blocked: true,
    caption: 'send, wait, parse, return: your code waits',
  },
  {
    mode: 'lazy',
    icon: 'i-mdi-sleep',
    tag: 'default',
    bar: { from: ACCESS, to: ACCESS + 30 },
    blocked: false,
    caption: 'nothing goes out until you read it. Never read? Never sent.',
  },
  {
    mode: 'preload',
    icon: 'i-mdi-rocket-launch-outline',
    tag: 'opt-in',
    bar: { from: CALL, to: CALL + 30 },
    blocked: false,
    caption: 'sent right away, in the background: concurrent with other calls',
  },
]
</script>

<template>
  <div class="modes">
    <div class="axis">
      <span class="mark" :style="{ left: `${CALL}%` }"><code>$pet = $client->getPet()</code></span>
      <span class="mark" :style="{ left: `${ACCESS}%` }"><code>echo $pet->name</code></span>
    </div>
    <div
      v-for="(lane, i) in lanes"
      :key="lane.mode"
      class="lane"
      :class="[lane.mode, { on: $clicks > i }]"
    >
      <div class="label">
        <div class="mode"><span :class="lane.icon" /> {{ lane.mode }}</div>
        <div class="tag">{{ lane.tag }}</div>
      </div>
      <div class="track">
        <span class="tick" :style="{ left: `${CALL}%` }" />
        <span class="tick" :style="{ left: `${ACCESS}%` }" />
        <span
          class="bar"
          :class="{ blocked: lane.blocked }"
          :style="{ left: `${lane.bar.from}%`, '--w': `${lane.bar.to - lane.bar.from}%` }"
        >HTTP</span>
        <span class="caption">{{ lane.caption }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.modes {
  display: flex;
  flex-direction: column;
  gap: 0.7rem;
}
.axis {
  position: relative;
  height: 1.6rem;
  margin-left: 8.5rem;
}
.axis .mark {
  position: absolute;
  transform: translateX(-0.6rem);
  font-size: 0.85rem;
  white-space: nowrap;
}
.lane {
  display: grid;
  grid-template-columns: 8rem 1fr;
  gap: 0.5rem;
  align-items: center;
  opacity: 0.15;
  transition: opacity 0.4s;
}
.lane.on {
  opacity: 1;
}
.label .mode {
  font-size: 1.35rem;
  font-weight: 700;
  display: flex;
  align-items: center;
  gap: 0.4rem;
}
.lane.eager .mode span { color: #9a9a97; }
.lane.lazy .mode span { color: var(--jaune); }
.lane.preload .mode span { color: var(--jane); }
.label .tag {
  font-size: 0.65rem;
  text-transform: uppercase;
  letter-spacing: 0.08em;
  opacity: 0.6;
}
.track {
  position: relative;
  height: 3.6rem;
  background: #f5f5f3;
  border-radius: 0.6rem;
}
.tick {
  position: absolute;
  top: 0;
  bottom: 0;
  border-left: 2px dashed #c9c9c6;
}
.bar {
  position: absolute;
  top: 0.45rem;
  height: 1.5rem;
  border-radius: 0.4rem;
  width: 0;
  overflow: hidden;
  font-size: 0.7rem;
  font-weight: 700;
  line-height: 1.5rem;
  padding-left: 0;
  color: var(--ink);
  transition: width 0.9s 0.15s cubic-bezier(0.2, 0.8, 0.2, 1), padding 0.9s 0.15s;
}
.lane.on .bar {
  width: var(--w);
  padding-left: 0.5rem;
}
.eager .bar { background: #d6d6d3; }
.lazy .bar { background: var(--jaune); }
.preload .bar { background: var(--jane); }
.bar.blocked {
  background: repeating-linear-gradient(-45deg, #d6d6d3, #d6d6d3 6px, #e8e8e5 6px, #e8e8e5 12px);
}
.caption {
  position: absolute;
  left: 0.6rem;
  bottom: 0.25rem;
  font-size: 0.72rem;
  opacity: 0.75;
}
</style>
