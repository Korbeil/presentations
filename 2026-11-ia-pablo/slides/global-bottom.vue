<template>
  <footer>
    <div
      class="absolute bottom-4 left-6 text-gray-400 font-300 text-xs -z-1"
      v-if="$slidev.nav.currentPage > 1"
    >
      IA &amp; PABLO — De l'ADE à l'orchestrateur <br>
      JoliCode | {{ (new Date()).toLocaleDateString('fr-FR', { year: 'numeric', month: 'long' }) }}
    </div>
  </footer>
</template>
