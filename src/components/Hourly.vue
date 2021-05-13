<template>
  <div class="hourlyComponents">
    <h2 class="hidden md:block mt-10 mb-4 text-center text-2xl">Hourly</h2>
    <div class="h-96 overflow-auto">
      <div v-for="hour in hourly.slice(1, 12)" :key="hour.dt">
        <div class="flex my-10">
          <p>{{ hour.weather[0].main }}</p>
          <img :src="{'../assets/'+currentWeather+'.svg)'}" alt="" width="60px">
          <p>{{ hour.dt | convertHours }}h : <span>{{ hour.temp }}°C</span></p>
        </div>
      </div>
    </div>

  </div>
</template>
<script>

export default {
  name: 'Hourly',
  props: {
    hourly: Array,
    hourlyWeather: null,
  },
  filters: {
    convertHours (unix_timestamp) {
      let date = new Date(unix_timestamp * 1000);
      let hours = date.getHours();
      return hours
    }
  },
  methods: {
    changeBackgroundImage() {
      switch (this.hour.weather[0].main) {
        case 'Sun':
          this.hourlyWeather = 'sun';
          break;
        case 'Clouds':
          this.hourlyWeather = 'cloud';
          break;
        default :
          this.hourlyWeather = 'sun';
      }
    }
  }
}
</script>