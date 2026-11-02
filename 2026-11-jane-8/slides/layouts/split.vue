<template>
  <div class="slidev-layout split h-full">
    <div class="split-left">
      <slot />
    </div>
    <div class="split-right">
      <slot name="right" />
    </div>
  </div>
</template>
