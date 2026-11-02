<script setup lang="ts">
import { useSlideContext } from '@slidev/client'

const { $clicks } = useSlideContext()

const rows = [
  {
    title: 'eager',
    at: 1,
    total: 't(pet) + t(owner)',
    bars: [
      { label: 'getPet', from: 0, w: 45, cls: 'grey' },
      { label: 'getOwner', from: 45, w: 45, cls: 'grey' },
    ],
  },
  {
    title: 'preload',
    at: 2,
    total: 'max(t(pet), t(owner))',
    bars: [
      { label: 'getPet', from: 0, w: 45, cls: 'teal' },
      { label: 'getOwner', from: 2, w: 40, cls: 'teal', lower: true },
    ],
  },
]
</script>

<template>
  <div class="race">
    <div v-for="row in rows" :key="row.title" class="row" :class="{ on: $clicks >= row.at }">
      <div class="head">
        <span class="title">{{ row.title }}</span>
        <span class="total">{{ row.total }}</span>
      </div>
      <div class="track">
        <span
          v-for="(b, i) in row.bars"
          :key="b.label"
          class="bar"
          :class="[b.cls, { lower: b.lower }]"
          :style="{ left: `${b.from}%`, '--w': `${b.w}%`, transitionDelay: row.title === 'eager' ? `${i * 0.9}s` : '0.1s' }"
        >{{ b.label }}</span>
      </div>
    </div>
  </div>
</template>

<style scoped>
.race {
  display: flex;
  flex-direction: column;
  gap: 1.2rem;
}
.row {
  opacity: 0.15;
  transition: opacity 0.4s;
}
.row.on {
  opacity: 1;
}
.head {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  margin-bottom: 0.35rem;
}
.title {
  font-weight: 700;
  font-size: 1.1rem;
}
.total {
  font-family: 'JetBrains Mono NL', monospace;
  font-size: 0.85rem;
  font-weight: 600;
}
.track {
  position: relative;
  height: 3.6rem;
  background: rgba(255, 255, 255, 0.55);
  border-radius: 0.6rem;
}
.bar {
  position: absolute;
  top: 0.35rem;
  height: 1.3rem;
  width: 0;
  overflow: hidden;
  white-space: nowrap;
  border-radius: 0.35rem;
  font-size: 0.7rem;
  font-weight: 700;
  line-height: 1.3rem;
  padding-left: 0;
  transition: width 0.9s cubic-bezier(0.2, 0.8, 0.2, 1), padding 0.9s;
}
.bar.lower {
  top: 1.95rem;
}
.row.on .bar {
  width: var(--w);
  padding-left: 0.5rem;
}
.bar.grey {
  background: #d6d6d3;
}
.row:first-child .bar:nth-child(2) {
  top: 1.95rem;
}
.bar.teal {
  background: var(--jane);
}
</style>
