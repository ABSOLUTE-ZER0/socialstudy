<template>
  <div id="app">

    <router-view /> <!--   need router-view to display route pages -->
  </div>
</template>

<script>
  export default {
    name: 'App',
    components: {}
  }
</script>

<style>
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
  }

  @media (max-width: 768px) {
    body {
      font-size: 0.5em !important;
    }
  }
</style>