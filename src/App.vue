<template>
  <div class="flex flex-col md:flex-row h-screen">
      <MainContent v-if="info"  :info="info"/>
    <SideBar/>
  </div>
</template>

<script lang="ts">
import {defineComponent} from 'vue'
const config = import.meta.env.VITE_NYT_API_KEY
import axios from 'axios'
import MainContent from './components/MainContent.vue'
import SideBar from './components/SideBar.vue'

export default defineComponent({
      name: 'App',
      components: {
        MainContent,
        SideBar,
      },

      data() {
        return {
          info: null,
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
        }
      },
    }
)
</script>

