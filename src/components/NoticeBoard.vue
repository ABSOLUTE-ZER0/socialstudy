<template>

  <b-row>
    <b-col lg="8" cols="12">
      <StartPost />
      <div v-for="post in posts" :key="post.id" style="padding: 2em" class="comp">
        <b-row>
          <b-col cols="2" md="auto">
            <b-img class="post-profile-img" :src="post.profileSrc" rounded="circle" alt="Circle image">
            </b-img>
          </b-col>
          <b-col>
            <p class="post-profile-name">{{post.name}}</p>
            <p class="post-profile-position">{{post.position}} | {{post.branch}}</p>
            <p class="post-profile-place">{{post.place}}</p>
          </b-col>
        </b-row>
        <b-row class="post-text" style="margin-top:1em">
          <p>{{post.text}}</p>
        </b-row>
        <b-row style="margin-top:1em">
          <b-img class="post-img" :src="post.image"></b-img>
        </b-row>
        <b-row v-if="post.hasVideo" class="post-video" style="margin-top:1em">
          <b-embed :src="post.video"></b-embed>
        </b-row>
      </div>
    </b-col>
    <b-col class="comp friends-col d-none d-lg-block" cols="3">
      <Friends />
    </b-col>
  </b-row>
</template>


<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
    white-space: pre-wrap;
  }

  .post-profile-img {
    width: 4em !important;
    height: 4em;
    margin-top: 0.5em;
  }

  .friends-col {
    margin-top: 12em;
    margin-left: 4%;
    height: fit-content;
  }

  .post-profile-name {
    font-size: 1.2em;
    font-weight: bold;
    margin: 0;
  }

  .post-img {
    width: 100%;
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

    .post-img {
      padding: 1em;
    }


    .post-video {
      margin-top: 0 !important;
      padding: 1em;
    }
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
            text: "Some random text goes here.\nWith video",
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
            text: "Some random text goes here.\nWith Image",
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
    methods: {}
  }
</script>