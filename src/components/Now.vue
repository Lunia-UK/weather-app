<template>
  <div class="md:w-4/5">
    <div class="flex flex-col md:flex-row md:justify-content-end-end p-2 lg:p-10">
      <h2 class="xl:text-9xl md:text-7xl text-8xl mr-12 lg:mr24 font-semibold">{{ current.temp }}°C</h2>
      <div class="flex flex-col h-24 lg:h-32 justify-around ">
        <h3 class="text-5xl lg:text-4xl md:text-3xl font-semibold">Today is {{ currentWeatherTitle }} day</h3>
        <p class="text-2xl lg:text-1xl">{{ currentWeatherParagraphe }}</p>
      </div>
    </div>
    <hr>
    <div class="flex justify-between p-5 text-white">
      <p>{{ time }}</p>
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
    this.loadTime();
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
    },
    loadTime() {
      const newDate = new Date();
      const months = ['January','Febuary','March','April','May','Jun','Jul','Aug','Sep','Oct','Nov','Dec'];
      const year = newDate.getFullYear();
      const month = months[newDate.getMonth()];
      const days = [ 'Sunday', 'Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday', 'Saturday'];
      const day = days[newDate.getDay()];
      const date = newDate.getDate();
      const hours = newDate.getHours()
      const minutes = "0" + newDate.getMinutes();
      const time =  hours + ':' + minutes.substr(-2) + ' - ' + day + ' ' + date + ' ' + month + ' ' + year
      return this.time = time
    }
  }
}
</script>