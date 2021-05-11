<template>
  <div class="relative bg-gray-600 md:w-4/5 h-full bg-center bg-no-repeat bg-cover" :style="{ 'background-image':'url(src/assets/'+currentWeather+'.jpg)'}" >
    <Now v-if="info" :current="info.current"/>
  </div>
</template>

<script>

import Now from './Now.vue'

export default {
  name: "MainContent",
  components: {
    Now
  },
  props: {
    info: null,
  },
  data() {
    return {
      currentWeather: null,
    };
  },
  created() {
    this.changeBackgroundImage();
  },
  methods: {
    changeBackgroundImage() {
      switch (this.info.current.weather[0].main) {
        case 'Sun':
          this.currentWeather = 'sun';
          break;
        case 'Clouds':
          this.currentWeather = 'clouds';
          break;
        default :
          this.currentWeather = 'day';
      }
    }
  }
}
</script>
