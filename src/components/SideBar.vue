<template>
  <div class="bg-white bg-opacity-50 md:w-1/5 md:h-full">
    <WeatherDetails :info="info"/>
  </div>
</template>

<script>
import WeatherDetails from '../components/WeatherDetails.vue'
export default {
  name: "SideBar",
  components: {WeatherDetails},
  props: {
    info: null,
  },
}
</script>