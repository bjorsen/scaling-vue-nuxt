<template>
  <div id="app">
    <nav-bar />
    <Nuxt />
  </div>
</template>

<script>
import NavBar from '@/components/NavBar.vue'

export default {
  components: { NavBar },
}
</script>

<style>
@import '@/assets/base.scss';
</style>
