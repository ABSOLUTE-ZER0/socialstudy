<template>
  <div id="app">

    <router-view /> <!--   need router-view to display route pages -->
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
body{
  background-color: rgb(224, 224, 224) !important;

}
</style>
