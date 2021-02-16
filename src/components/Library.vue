<template>
          <div style="padding: 2em" class="comp">
            <b-row>
              <b-col cols="12" md="auto">
                <b-img class="post-profile-img" src="https://placekitten.com/1000/300" rounded="circle" alt="Circle image">
                </b-img>
              </b-col>
              <b-col>
                <p class="post-profile-name">Friends Name</p>
                <p class="post-profile-position">Position | Branch</p>
                <p class="post-profile-place">Place</p>
              </b-col>
            </b-row>
            <b-row style="margin-top:1em">
              <p>Some random text goes here</p>
            </b-row>
            <b-row style="margin-top:1em">
              <b-img></b-img>
            </b-row>
            <b-row v-if=false style="margin-top:1em">
              <b-embed></b-embed>
          `</b-row>
          </div>
</template>


<style scoped>



</style>



<script>
  export default {
    data() {
      return {

      }
    },
    components: {
    }
  }
</script>