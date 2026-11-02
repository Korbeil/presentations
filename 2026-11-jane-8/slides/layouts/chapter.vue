<template>
  <div class="slidev-layout chapter h-full">
    <div class="chapter-number">{{ $frontmatter.number }}</div>
    <div class="chapter-body">
      <slot />
    </div>
  </div>
</template>
