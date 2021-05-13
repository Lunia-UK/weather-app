<template>
  <div class="flex flex-col items-end md:flex-row h-screen bg-gray-600 bg-center bg-no-repeat bg-cover" :style="info ? { 'background-image':'url(src/assets/'+currentWeather+'.jpg)'} : ''">
    <Now v-if="info" :current="info.current"/>
    <SideBar v-if="info"  :info="info"/>
  </div>
</template>

<script lang="ts">
import {defineComponent} from 'vue'
const config = import.meta.env.VITE_NYT_API_KEY
import axios from 'axios'
import Now from './components/Now.vue'
import SideBar from './components/SideBar.vue'

export default defineComponent({
      name: 'App',
      components: {
        Now,
        SideBar,
      },

      data() {
        return {
          info: null,
          currentWeather: null,
        };
      },
      created() {
        this.loadData()
      },
      methods: {
        async loadData () {
          const response = await axios.get('https://api.openweathermap.org/data/2.5/onecall',{
            params: {
              lat:51.228236,
              lon:0.544608,
              units:'metric',
              appid: config
            }
          });
          this.info = response.data;
          this.changeBackgroundImage();
        },
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
      },
    }
)
</script>

