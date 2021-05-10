<template>
  <div class="absolute inset-x-0 bottom-0">
    <div class="flex items-center p-10">
      <h2 class="text-9xl mr-28 font-semibold">{{ current.temp }}°C</h2>
      <div class="">
        <h3 class="text-5xl">Today is a rainy day</h3>
        <p class="text-2xl">Don't forget an umbrella</p>
      </div>
    </div>
    <hr>
    <div class="flex justify-between p-5">
      <p>{{time}}</p>
      <p class="uppercase">maidstone, gb</p>
    </div>
  </div>
</template>

<script>

export default {
name: "Now",
  props: {
    current: {}
  }
}
</script>