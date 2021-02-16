<template>
  <div>
    <b-row style="padding: 1em">
      <h4 style="font-weight: bold">Online Friends</h4>
    </b-row>
    <b-row v-for="friend in friends" :key="friend" class="friends-row">
      <b-col cols="12" md="auto">
        <b-img class="friends-img" :src="friend.src" rounded="circle" alt="Circle image"></b-img>
      </b-col>
      <b-col>
        <p class="friends-name">{{friend.name}}</p>
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

.friends-row{
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
        siteName: "",
        friends: [
          {name: "Friend Name 1", src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"},
          {name: "Friend Name 2", src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"},
        ]
      }
    },
    components: {
    },
    methods: {

    }
  }
</script>