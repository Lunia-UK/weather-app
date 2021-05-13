<template>
  <div class="bg-white bg-opacity-50 w-full md:w-1/5 md:h-full">
    <WeatherDetails :info="info"/>
    <Hourly :hourly="info.hourly"/>
  </div>
</template>

<script>
import WeatherDetails from '../components/WeatherDetails.vue'
import Hourly from '../components/Hourly.vue'
export default {
  name: "SideBar",
  components: {WeatherDetails, Hourly},
  props: {
    info: null,
  },
}
</script>