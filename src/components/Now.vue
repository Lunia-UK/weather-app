<template>
  <div class="absolute inset-x-0 bottom-0 h-16">
    <h1>{{ current.temp }}</h1>
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