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
    font-size: 0.85em;
  }

  .form-group{
    margin-bottom: 0 !important;
  }

  .comp {
    background-color: white !important;
    border-radius: 1em;
    margin: 10px;
    margin-left: 0 !important;
    margin-right: 0 !important;
    box-shadow: 0 1px 4px rgba(0, 0, 0, 0.3), 0 0 40px rgba(0, 0, 0, 0.1);
  }

  shadow {
    box-shadow: 0 1px 4px rgba(0, 0, 0, 0.3), 0 0 40px rgba(0, 0, 0, 0.1);
  }

  .comp:before,
  .comp:after,
  .shadow:before,
  .shadow:after {
    box-shadow: 0 0 20px rgba(0, 0, 0, 0.8);
    border-radius: 100px / 10px;
  }

  .comp:after,
  .shadow:after {
    right: 10px;
    left: auto;
    transform: skew(8deg) rotate(3deg);
  }



  /* modals */

  


  @media (max-width: 768px) {
    body {
      font-size: 0.5em !important;
    }
  }
</style>