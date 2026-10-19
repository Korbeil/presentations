<template>
  <span
    v-if="$slidev.nav.currentSlideRoute?.meta?.slide?.frontmatter?.tag"
    class="section-tag"
  >{{ $slidev.nav.currentSlideRoute.meta.slide.frontmatter.tag }}</span>
  <span
    v-if="$slidev.nav.currentPage > 1"
    class="absolute bottom-4 right-6 text-gray-500 font-300"
  >{{ $slidev.nav.currentPage }}</span>
</template>
