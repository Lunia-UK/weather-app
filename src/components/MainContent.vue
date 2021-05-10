<template>
  <div class="relative bg-gray-600 md:w-4/5 h-full bg-center bg-no-repeat bg-cover" style="background-image: url('src/assets/day.jpg')">
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
    info: {}
  },
}
</script>