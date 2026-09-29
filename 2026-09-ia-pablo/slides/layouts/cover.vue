<template>
  <div class="slidev-layout cover">
    <span class="ia-logo"><mdi-robot-happy class="ia-icon" /></span>
    <slot />
    <div class="text-true-gray-400 pl-8 mt-8">
      {{ $slidev.configs.trainer }} –
      {{ (new Date()).toLocaleDateString('fr-FR', { year: 'numeric', month: 'long'}) }}
    </div>
    <span class="jolicode-logo">
      <img src="/images/jolicode.svg" alt="jolicode logo" />
    </span>
  </div>
</template>
