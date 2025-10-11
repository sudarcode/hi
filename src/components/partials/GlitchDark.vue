<template>
  <VueTextGlitch
    fill="#d1d5db"
    :text="text"
    background
    highlight2="cyan"
  />
</template>

<script>
import VueTextGlitch from 'vue-text-glitch';
export default {
  components: { VueTextGlitch },
  props: ['text'],
};
</script>
