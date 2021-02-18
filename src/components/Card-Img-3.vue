<template>
  <b-card class="card" img-left :img-src="src">
    <b-card-body style="margin-top:-1em" class="body">
      <b-card-title> {{name}} </b-card-title>
      <b-card-sub-title class="mb-2"> {{designation}} | {{group}}</b-card-sub-title>
      <b-card-sub-title class="mb-2"> {{institute}} </b-card-sub-title>
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
    border-radius: 0;
  }
</style>

<script>
  export default {
    props: {
      name: String,
      src: String,
      designation: String,
      group: String,
      institute: String

    }
  }
</script>