<template>
  <div class="relative bg-gray-600 md:w-4/5 h-full">
    <Now :temperature="info.current.temp"/>
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