<template>

  <b-row>
    <b-col class="" cols="8">
      <StartPost />
      <div v-for="post in posts" :key="post.id" style="padding: 2em" class="comp">
        <b-row>
          <b-col cols="12" md="auto">
            <b-img class="post-profile-img" :src="post.profileSrc" rounded="circle" alt="Circle image">
            </b-img>
          </b-col>
          <b-col>
            <p class="post-profile-name">{{post.name}}</p>
            <p class="post-profile-position">{{post.position}} | {{post.branch}}</p>
            <p class="post-profile-place">{{post.place}}</p>
          </b-col>
        </b-row>
        <b-row style="margin-top:1em">
          <p>{{post.text}}</p>
        </b-row>
        <b-row style="margin-top:1em">
          <b-img class="post-img" :src="post.image"></b-img>
        </b-row>
        <b-row v-if="post.hasVideo" style="margin-top:1em">
          <b-embed :src="post.video"></b-embed>
        </b-row>
      </div>
    </b-col>
    <b-col style="margin-top: 10em; margin-left: 4%" class="comp" cols="3">
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

  .post-img {
    width: 100%;
    margin: 0 2em;
  }

  .post-profile-position {
    margin: 0;
  }
</style>



<script>
  import StartPost from "./StartPost"
  import Friends from "./Friends"

  export default {
    data() {
      return {
        siteName: "",
        posts: [{
            id: "1",
            name: "Friends Name",
            position: "Position",
            branch: "Branch",
            place: "Place",
            profileSrc: "https://placekitten.com/1000/300",
            text: "Some random text goes here",
            image: "",
            video: "https://www.youtube.com/embed/wrspWfZ52R8",
            hasVideo: true
          },
          {
            id: "2",
            name: "Friends Name",
            position: "Position",
            branch: "Branch",
            place: "Place",
            profileSrc: "https://placekitten.com/1000/300",
            text: "Some random text goes here",
            image: "https://picsum.photos/300/150/?image=41",
            video: "",
            hasVideo: false
          }

        ]
      }
    },
    components: {
      StartPost,
      Friends
    },
    methods: {

    }
  }
</script>