<template>
  <footer>
    <div
      class="absolute bottom-4 left-6 text-gray-400 font-300 text-xs -z-1"
      v-if="$slidev.nav.currentPage > 1"
    >
      Jane 8 — API made easier, again <br>
      JoliCode | {{ (new Date()).toLocaleDateString('en-GB', { year: 'numeric', month: 'long' }) }}
    </div>
  </footer>
</template>
