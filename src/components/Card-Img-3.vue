<template>
  <b-card @click="log" img-left :img-src="src">
    <b-card-body class="body profile" :style="styles">
      <b-card-title class="title"> {{name}} </b-card-title>
      <b-card-sub-title class="mb-2 sub"> {{sub1}} | {{sub2}}</b-card-sub-title>
      <b-card-sub-title class="mb-2 sub"> {{sub3}} </b-card-sub-title>
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
    pointer-events: all;
  }


  @media (max-width: 768px) {
      .card-img-left {
    border: 0;
    width: 6em;
    height: 6em;
    margin-top: 1em;
  }
  .card{
    margin: 1em;
  }
    .title{
      font-size: 1.3em;
    }
    .sub{
      font-size: 1em;
    }
    .body{
      margin-top: -1em !important;
      padding: 0;

    }
        .profile{
      margin-top: 0 !important;
      padding: 0;

    }
    .card-body{
      padding: 1em .5em 0;

    }
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
    },
    methods: {
      log(){
        console.log("hello");
      }
    },
  }
</script>