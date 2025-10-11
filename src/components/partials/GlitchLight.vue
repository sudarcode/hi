<template>
  <VueTextGlitch
    fill="#374151"
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
