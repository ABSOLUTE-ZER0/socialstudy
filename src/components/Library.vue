<template>

  <b-row>
    <b-col class="" lg="8" cols="12">
      <b-row class="comp">
        <b-button variant="info" class="create-btn">+ Create / Upload Study Material</b-button>
      </b-row>
      <div style="padding: 2em" class="comp">
        <b-row>
          <b-col cols="2" md="auto">
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
          <p class="post-text">Some random text goes here</p>
        </b-row>
        <b-row style="margin-top:1em">
          <b-img></b-img>
        </b-row>
        <b-row v-if=false style="margin-top:1em">
          <b-embed></b-embed>
        </b-row>
      </div>
    </b-col>
    <b-col class="friends-col comp d-none d-lg-block" cols="3">
      <Friends />
    </b-col>
  </b-row>
</template>


<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  .friends-col {
    margin-top: 10em;
    margin-left: 4%;
    height: fit-content;
  }


  .create-btn {
    width: 100%;
    margin: 1em;
    font-size: 2em;
    border-radius: 0.5em;
    border: 0;
    color: gray;
    background-color: rgba(127, 255, 212, 0.233);
  }

  .post-profile-img {
    width: 4em !important;
    height: 4em;
    margin-top: 0.5em;
  }

  .post-profile-name {
    font-size: 1.2em;
    font-weight: bold;
    margin: 0;
  }

  .post-profile-position {
    margin: 0;
  }

  @media (max-width: 768px) {
    .post-profile-img {
      width: 5em !important;
      height: 5em;
      margin-top: 0 !important;
    }

    .post-text {
      margin: 0 !important;
    }

    .post-video {
      margin-top: 0 !important;
    }
  }
</style>



<script>
  import Friends from "./Friends"

  export default {
    data() {
      return {
        siteName: ""
      }
    },
    components: {
      Friends
    },
    methods: {

    }
  }
</script>