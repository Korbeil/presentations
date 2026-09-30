<template>
  <div class="slidev-layout cover">
    <span class="jane-logo">
      <img src="/images/jane.png" alt="JanePHP" />
    </span>

    <slot />

    <div class="text-true-gray-400 pl-8 mt-8">
      {{ $slidev.configs.trainer }} – {{ (new Date()).toLocaleDateString('fr-FR', { year: 'numeric', month: 'long'}) }}
    </div>

    <span class="jolicode-logo">
      <img src="/images/jolicode.svg" alt="jolicode logo" />
    </span>
  </div>
</template>
