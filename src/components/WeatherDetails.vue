<template>
  <h2 class="hidden md:block my-4 text-center text-2xl">Weather Details</h2>
  <div class="flex flex-row md:flex-col justify-around">
    <div class="flex flex-col md:flex-row items-center border-b border-gray-200 py-3 px-6 text-left whitespace-nowrap">
      <div class="mr-2">
        Humidity
      </div>
      <span class="font-medium">{{ info.current.humidity }}</span>
    </div>
    <div class="hidden md:flex items-center border-b border-gray-200 py-3 px-6 text-left whitespace-nowrap">
      <div class="mr-2">
        UV
      </div>
      <span class="font-medium">{{ info.current.uvi }}</span>
    </div>
    <div class="hidden md:flex items-center border-b border-gray-200 py-3 px-6 text-left whitespace-nowrap">
      <div class="mr-2">
        Pressure
      </div>
      <span class="font-medium">{{ info.current.pressure }}</span>
    </div>
    <div class="hidden md:flex items-center border-b border-gray-200 py-3 px-6 text-left whitespace-nowrap">
      <div class="mr-2">
        Clouds
      </div>
      <span class="font-medium">{{ info.current.clouds }}</span>
    </div>
    <div class="flex flex-col md:flex-row items-center border-b border-gray-200 py-3 px-6 text-left whitespace-nowrap">
      <div class="mr-2">
        Visibility
      </div>
      <span class="font-medium">{{ info.current.visibility }}</span>
    </div>
    <div class="flex flex-col md:flex-row items-center border-b border-gray-200 py-3 px-6 text-left whitespace-nowrap">
      <div class="mr-2">
        Wind speed
      </div>
      <span class="font-medium">{{ info.current.wind_speed }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "WeatherDetails",
  props: {
    info: null,
  },
}
</script>

<style scoped>

</style>