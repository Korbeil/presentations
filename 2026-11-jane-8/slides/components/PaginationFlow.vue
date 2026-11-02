<script setup lang="ts">
import { computed } from 'vue'
import { useSlideContext } from '@slidev/client'

const { $clicks } = useSlideContext()

// click 1: page 1, click 2: page 2, click 3: `break`, pages 3 and 4 are never requested
const pages = [1, 2, 3, 4]
const stopped = computed(() => $clicks.value >= 3)

function state(page: number) {
  if (stopped.value && page > 2) return 'never'
  if ($clicks.value >= page) return 'fetched'
  return 'idle'
}
</script>

<template>
  <div class="flow">
    <div
      v-for="page in pages"
      :key="page"
      class="page"
      :class="state(page)"
    >
      <div class="head">
        <span>GET ?cursor={{ page === 1 ? '' : `c${page - 1}` }}</span>
        <span class="status">{{ state(page) === 'never' ? 'never sent' : state(page) === 'fetched' ? '200' : '' }}</span>
      </div>
      <div class="items">
        <span v-for="n in 5" :key="n" class="item" :style="{ transitionDelay: `${0.25 + n * 0.08}s` }">Item</span>
      </div>
    </div>
    <div class="break" :class="{ on: stopped }"><code>break;</code></div>
  </div>
</template>

<style scoped>
.flow {
  position: relative;
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
}
.page {
  background: #f5f5f3;
  border-radius: 0.6rem;
  padding: 0.45rem 0.8rem;
  border: 2px solid transparent;
  transition: all 0.4s;
}
.page .head {
  display: flex;
  justify-content: space-between;
  font-family: 'JetBrains Mono NL', monospace;
  font-size: 0.7rem;
  opacity: 0.6;
}
.page .status {
  font-weight: 700;
}
.items {
  display: flex;
  gap: 0.35rem;
  margin-top: 0.3rem;
}
.item {
  flex: 1;
  text-align: center;
  font-size: 0.65rem;
  font-weight: 600;
  padding: 0.15rem 0;
  border-radius: 0.3rem;
  background: #e6e6e3;
  color: transparent;
  transition: all 0.35s;
}
.page.fetched {
  background: #fff;
  border-color: var(--jane);
}
.page.fetched .head {
  opacity: 1;
}
.page.fetched .status {
  color: #1f9d8f;
}
.page.fetched .item {
  background: var(--jane-pale);
  color: var(--ink);
}
.page.never {
  opacity: 0.35;
  border-style: dashed;
  border-color: #c9c9c6;
}
.page.never .status {
  color: #c0392b;
}
.break {
  position: absolute;
  left: -0.5rem;
  right: -0.5rem;
  top: calc(50% - 0.1rem);
  border-top: 3px solid #e74c3c;
  opacity: 0;
  transform: scaleX(0);
  transform-origin: left;
  transition: all 0.5s cubic-bezier(0.2, 0.8, 0.2, 1);
}
.break.on {
  opacity: 1;
  transform: scaleX(1);
}
.break code {
  position: absolute;
  right: 0;
  top: -0.85rem;
  background: #e74c3c !important;
  color: #fff !important;
  font-size: 0.75rem;
}
</style>
