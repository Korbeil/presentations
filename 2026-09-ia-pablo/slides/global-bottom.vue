<template>
  <footer>
    <div
      class="absolute bottom-4 left-6 text-gray-400 font-300 text-xs -z-1"
      v-if="$slidev.nav.currentPage > 1"
    >
      IA & PABLO — From an ADE to an Orchestrator <br>
      JoliCode | {{ (new Date()).toLocaleDateString('fr-FR', { year: 'numeric', month: 'long' }) }}
    </div>
    <span
      v-if="$slidev.nav.currentPage > 1"
      class="absolute bottom-4 right-6 text-gray-500 font-300"
    >{{ $slidev.nav.currentPage }}</span>
  </footer>
</template>
