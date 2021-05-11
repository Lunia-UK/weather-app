<template>
  <div class="absolute inset-x-0 bottom-0">
    <div class="flex items-center p-10">
      <h2 class="text-9xl mr-28 font-semibold">{{ current.temp }}°C</h2>
      <div class="flex flex-col h-32 justify-around ">
        <h3 class="text-5xl font-semibold">Today is {{ currentWeatherTitle }} day</h3>
        <p class="text-2xl">{{ currentWeatherParagraphe }}</p>
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
  },
  data() {
    return {
      currentWeatherTitle: null,
    };
  },
  created() {
    this.changeTitle();
  },
  methods: {
    changeTitle() {
      switch (this.current.weather[0].main) {
        case 'Sun':
          this.currentWeatherTitle = 'sun';
          this.currentWeatherParagraphe = 'Enjoy your day !';
          break;
        case 'Clouds':
          this.currentWeatherTitle = 'cloudy';
          this.currentWeatherParagraphe = 'Enjoy your day !';
          break;
        case 'Rain':
          this.currentWeatherTitle = 'rainy';
          this.currentWeatherParagraphe = 'Don\'t forget an umbrella';
          break;
        default :
          this.currentWeatherTitle = 'day';
      }
    }
  }
}
</script>