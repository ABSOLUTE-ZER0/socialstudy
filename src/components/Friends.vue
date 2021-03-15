<template>
  <div class="friends-div">
    <b-row @mousedown.prevent="" @click="clicked=!clicked" class="title">
      <h4 class="title-text">Online Friends</h4>
    </b-row>
    <div class="test" v-if="clicked">
      <b-row v-for="friend in friends" :key="friend" class="friends-row">
        <b-col cols="12" md="auto">
          <b-img class="friends-img" :src="friend.src" rounded="circle" alt="Circle image"></b-img>
        </b-col>
        <b-col>
          <p class="friends-name">{{friend.name}}</p>
        </b-col>
      </b-row>
    </div>

  </div>
</template>


<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  .friends-div {
    position: fixed;
    bottom: 0;
    right: 2em;
    min-width: fit-content;
    width: 15%;
    background-color: white;
    border-top-left-radius: 1em;
    border-top-right-radius: 1em;
    overflow-x: hidden;
    max-height: 80vh;
    box-shadow: 1px 0 1px 1px rgb(0 0 0 / 10%);
  }

  .title-text {
    font-weight: bold;
    width: 100%;
    font-size: 1.5em;
    margin: 0.1em 0;
  }

  .title {
    padding: 0.5em;
    cursor: pointer;
    text-align: center;
    width: 100%;
    background-color: #01C4C9;
    margin: 0;
    border-top-left-radius: 1em;
    border-top-right-radius: 1em;
    position: sticky;
    top: 0;
    z-index: 10;
    border-bottom: 1px solid black;
  }

  .test {
    overflow: hidden;
    animation: appear 1s;
  }

  .friends-row {
    margin: 1em;
  }

  .friends-name {
    font-size: 1.4em;
    margin-top: 0.4em;
  }

  .friends-img {
    width: 3em !important;
    height: 3em;
  }

  @keyframes appear {
    from {
      max-height: 0;
    }

    to {
      max-height: 80vh;
    }
  }
</style>




<script>
  export default {
    data() {
      return {
        clicked: false,
        siteName: "",
        friends: [{
            name: "Friend Name 1",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          },
          {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }, {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }, {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }, {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }, {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }, {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }, {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }, {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }, {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }, {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          },
          {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          },
          {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          },
          {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          },
          {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          },
          {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          },
          {
            name: "Friend Name 2",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          },

        ]
      }
    },
    components: {},
    methods: {

      animate() {

      }

    }
  }
</script>