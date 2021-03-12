<template>
  <b-row>
    <b-col lg="7">
      <h1 class="title">All your connections</h1>
      <b-row v-for="friend in friends" :key="friend" class="comp">
        <b-col cols="8">
          <CardImg3 styles="margin-top: -1em" :src="friend.src" :name="friend.name" :sub1="friend.year"
            :sub2="friend.group" :sub3="friend.institute" />
        </b-col>
        <b-col class="gone" cols="4">
          <b-button class="faculty-button" variant="info">View Profile
          </b-button>
        </b-col>
      </b-row>
    </b-col>
    <b-col lg="4">
      <h1 class="title">Pending Connections</h1>
      <div class="comp req-div">
      <b-row v-for="friend in friends" :key="friend" >
        <b-col cols="3">
          <CardImg className="req" :src="friend.src" />
        </b-col>
        <b-col class="gone" cols="8">
          <b-button class="req-btn" variant="info">Accept
          </b-button>
          <b-button class="req-btn" variant="danger">Decline
          </b-button>
        </b-col>
      </b-row>
      </div>

      <b-row class="comp">
        <h1 class="title">Groups Created</h1>
        <b-button class="create-btn">+ Create Group</b-button>
      </b-row>
    </b-col>


  </b-row>

</template>


<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  .title {
    padding: 1em 1em 0;
    font-size: 2em;
    font-weight: bold;
  }

  .req-btn{
    width: 40%;
    font-size: 1em;
    margin: 1.5em 0.5em 0;
  }

  .req-div{
    height: 30em;
    overflow-y: scroll;
    overflow-x: hidden;
  }


  .filter {
    text-align: center;
    font-weight: bold;
    font-size: 1.2em;
  }


  .faculty-button {
    margin: 2.5em 0.5em 0;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 80%;
  }

  .create-btn{
    height: fit-content;
    padding: 0.5em;
    font-size: 1em;
    border-radius: 2em;
    margin-top: 2em;
  }


  @media (max-width: 768px) {
    

  }
</style>


<script>
  import CardImg3 from './Card-Img-3';
  import CardImg from './Card-Img';
  export default {
    data() {
      return {
        activeTab: "Enrollment",
        friends: [{
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        },
        {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        },
        {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        },
        {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        },
        {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        },
        {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        },
        {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        },
        {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        },
        {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        },
        {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        }
        ]
      }
    },

    components: {
      CardImg3,
      CardImg
    }


  }
</script>