<template>
  <b-card class="card" img-left :img-src="src">
    <b-card-body :style="styles" >
      <b-card-title> {{name}} </b-card-title>
      <b-card-sub-title class="mb-2"> {{sub1}} | {{sub2}}</b-card-sub-title>
      <b-card-sub-title class="mb-2"> {{sub3}} </b-card-sub-title>
    </b-card-body>
  </b-card>
</template>

<style scoped>
  .card-img-left {
    border: 0;
    width: 5em;
    height: 5em;
    margin-top: 1.5em;
    border-radius: 50%;
  }

  .card {
    margin: 1em 2em 0;
    border: 0;
    width: 100%;
  }
</style>

<script>
  export default {
    props: {
      name: String,
      src: String,
      sub1: String,
      sub2: String,
      sub3: String,
      styles: String
    }
  }
</script>