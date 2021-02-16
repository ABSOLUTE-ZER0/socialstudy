<template>
  <div>
    <b-row style="padding: 1em">
      <h4 style="font-weight: bold">Online Friends</h4>
    </b-row>
    <b-row class="friends-row">
      <b-col cols="12" md="auto">
        <b-img class="friends-img" src="https://placekitten.com/1000/300" rounded="circle" alt="Circle image"></b-img>
      </b-col>
      <b-col>
        <p class="friends-name">Friends Name</p>
      </b-col>
    </b-row>
  </div>

</template>


<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }



  .friends-name {
    font-size: 1.4em;
    margin-top: 0.8em;
  }

  .friends-img {
    width: 4em !important;
    height: 4em;
  }
</style>



<script>
  export default {
    data() {
      return {
        siteName: ""
      }
    },
    components: {
    },
    methods: {

    }
  }
</script>