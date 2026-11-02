<script setup lang="ts">
import { computed } from 'vue'
import { useSlideContext } from '@slidev/client'

const { $clicks } = useSlideContext()

const layers = [
  { name: 'PSR-7 messages', note: 'request, response, streams for every body' },
  { name: 'PSR-17 factories', note: 'to build those messages' },
  { name: 'HTTPlug PluginClient', note: 'plugins: host, path, auth…' },
  { name: 'PSR-18 client', note: 'blocking: send, wait, parse' },
]

const transportSpotted = computed(() => $clicks.value >= 1)
const collapsed = computed(() => $clicks.value >= 2)
</script>

<template>
  <div class="stack">
    <div class="layer you">Your code</div>
    <div class="middle" :class="{ collapsed }">
      <div v-for="(l, i) in layers" :key="l.name" class="layer mid" :style="{ transitionDelay: `${i * 70}ms` }">
        <span class="name">{{ l.name }}</span>
        <span class="note">{{ l.note }}</span>
      </div>
    </div>
    <div class="layer transport" :class="{ spotted: transportSpotted, collapsed }">
      <span class="name">Symfony HttpClient</span>
      <span class="note">{{ collapsed ? 'directly. Natively async.' : 'what most of you plugged in anyway' }}</span>
    </div>
  </div>
</template>

<style scoped>
.stack {
  display: flex;
  flex-direction: column;
  gap: 0.35rem;
}
.layer {
  border-radius: 0.6rem;
  padding: 0.45rem 1rem;
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 1rem;
  font-weight: 600;
  transition: all 0.5s cubic-bezier(0.2, 0.8, 0.2, 1);
}
.layer .note {
  font-size: 0.75rem;
  font-weight: 400;
  opacity: 0.7;
  text-align: right;
}
.you {
  background: var(--ink);
  color: var(--jaune);
}
.middle {
  display: flex;
  flex-direction: column;
  gap: 0.35rem;
  max-height: 16rem;
  transition: max-height 0.6s cubic-bezier(0.2, 0.8, 0.2, 1), gap 0.6s;
}
.mid {
  background: #f1f1ef;
  border: 1px dashed #c9c9c6;
  max-height: 3rem;
}
.middle.collapsed {
  max-height: 0;
  gap: 0;
}
.middle.collapsed .mid {
  opacity: 0;
  transform: scaleY(0.2) translateX(2rem);
  max-height: 0;
  padding-top: 0;
  padding-bottom: 0;
  border-width: 0;
}
.transport {
  background: #f1f1ef;
  border: 1px solid #c9c9c6;
}
.transport.spotted {
  background: var(--jane-pale);
  border-color: var(--jane);
}
.transport.collapsed {
  background: var(--jane);
  color: var(--ink);
  padding-top: 1.1rem;
  padding-bottom: 1.1rem;
  font-size: 1.3rem;
  box-shadow: 0 10px 25px rgba(76, 209, 197, 0.35);
}
</style>
