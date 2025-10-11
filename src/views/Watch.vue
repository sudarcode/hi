<template>
  <div class="text-gray-300">
    <div class="flex flex-col items-center justify-center h-screen">
      <div
        data-aos="fade"
        data-aos-duration="1000"
        class="flex flex-col items-center"
      >
        <Glitch
          :text="currentTime"
          size="large"
        />
      </div>
    </div>
  </div>
</template>

<script>
import Glitch from '../components/partials/Glitch.vue';
export default {
  name: 'Watch',
  metaInfo: {
    title: 'Watch -',
    meta: [
      { vmid: 'title', name: 'title', content: 'Watch - Raya Sabari' },
      { vmid: 'description', name: 'description', content: 'What time is it' },
    ],
  },
  components: {
    Glitch,
  },
  data() {
    return {
      currentTime: ''
    }
  },
  mounted() {
    window.scrollTo(0, 0);
    this.updateTime() // update pertama kali
    this.timer = setInterval(this.updateTime, 1000) // update tiap 1 detik
  },
  beforeUnmount() {
    clearInterval(this.timer) // bersihin biar ga memory leak
  },
  methods: {
    updateTime() {
      const now = new Date()
      const hours = String(now.getHours()).padStart(2, '0')
      const minutes = String(now.getMinutes()).padStart(2, '0')
      this.currentTime = `${hours}:${minutes}`
    }
  }
};
</script>
