<template>
  <div id="app">
    <Home />
  </div>
</template>

<script>
import Home from '@/components/Home.vue'
//import Header from '@/components/Header.vue'

export default {
  name: 'App',
  components: {
    Home
    //Header
  }
}
</script>

<style lang="scss">
body {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
}
</style>
