<template>
  <div class="absolute inset-x-0 bottom-0 h-16">
    <h1>{{ temperature.temp }}</h1>
  </div>
</template>

<script>

export default {
name: "Now",
  props: {
    temperature: {}
  }
}
</script>