<template>
  <div class="main-div">
    <b-container fluid>
      <b-row>
          <b-col cols="3">
            <Tools />
          </b-col>

        <b-col class="" cols="6">

          <StartPost />

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
        </b-col>



        <b-col style="margin-top: 10em; margin-left: 4%" class="comp" cols="2">
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


        </b-col>

      </b-row>
    </b-container>
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

  .post-profile-img{
    width: 4em !important;
    height: 4em;
    margin-top: 0.5em;
  }
  .post-profile-name{
    font-size: 1.2em;
    font-weight: bold;
    margin: 0;
  }

  .post-profile-position{
    margin: 0;
  }


</style>



<script>
import StartPost from "./StartPost"
import Tools from "./DetailsAndTools"
  export default {
    data() {
      return {

      }
    },
    components: {
      StartPost,
      Tools
    }
  }
</script>