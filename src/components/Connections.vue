<template>
  <div>
    <b-row class="comp">
      <b-col cols="10">
        <b-button style="float: left;" class="con-group-btn" variant="info">+ Create Group</b-button>
        <b-button style="float: right;" class="con-group-btn" variant="outline-info">Groups</b-button>
      </b-col>
      <b-col class="filter-col" cols="2">
        <b-navbar>
          <b-navbar-nav>
            <b-nav-item class="filter" @click="pageName='';changePage()">
              <i class="fas fa-2x icon fa-clipboard-check"></i> Select Filter
            </b-nav-item>
          </b-navbar-nav>
        </b-navbar>
      </b-col>
    </b-row>

    <b-button @click="activeTab='Enrollment'" class="con-btn" variant="outline-info">Enrollment</b-button>
    <b-button @click="activeTab='Faculty/Admin'" class="con-btn" variant="outline-info">Faculty/Admin</b-button>
    <b-button @click="activeTab='Friends'" class="con-btn" variant="outline-info">Friends</b-button>

    <div v-if="activeTab == 'Enrollment'">
      <b-row v-for="enroll in enrollment" :key="enroll" class="comp">

        <b-col md="8" cols="7">
          <CardImg :src="enroll.src" :name="enroll.name" :sub1="enroll.institute" />
        </b-col>

        <b-col class="gone" md="4" cols="5">
          <b-button class="enrollment-button" variant="info">View Page
          </b-button>
        </b-col>
      </b-row>

    </div>


    <div v-if="activeTab=='Faculty/Admin'">
      <b-row v-for="teacher in faculty" :key="teacher" class="comp">
        <b-col cols="8">
          <CardImg3 styles="margin-top: -1em;" :src="teacher.src" :name="teacher.name" :sub1="teacher.designation"
            :sub2="teacher.group" :sub3="teacher.institute" />
        </b-col>
        <b-col class="gone" cols="4">
          <b-button class="faculty-button" variant="info">View Profile
          </b-button>
        </b-col>
      </b-row>
    </div>

    <div v-if="activeTab=='Friends'">
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
    </div>

  </div>

</template>


<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  .filter {
    text-align: center;
    font-weight: bold;
    font-size: 1.2em;
  }

  .con-btn {
    margin: 1em;
    width: 20%;
    border-radius: 1em;
    font-size: 1.5em;

  }

  .con-group-btn {
    margin: 1.5em;
    width: 30%;
    border-radius: 1em;
    font-size: 1.5em;
  }

  .enrollment-button {
    margin: 2em 0.5em;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 80%;
  }


  .faculty-button {
    margin: 2.5em 0.5em 0;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 80%;
  }


  @media (max-width: 768px) {
    .con-group-btn {
      float: none !important;
      margin: 1em;
      width: 40%;
      border-radius: 1em;
      font-size: 1.2em;
    }

    .navbar {
      padding: 0;
    }

    .filter-col {
      padding: 0;
      margin-left: -2em;

    }

    .con-btn {
      margin: 0.5em;
      width: 30%;
      border-radius: 1em;
      font-size: 1.2em;

    }

    .gone {
      display: none;
    }

  }
</style>


<script>
  import CardImg3 from './Card-Img-3';
  import CardImg from './Card-Img'
  export default {
    data() {
      return {
        activeTab: "Enrollment",
        enrollment: [{
            name: "w3schools",
            institute: "Online Learning Platform",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          },
          {
            name: "w3schools",
            institute: "Online Learning Platform",
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          }

        ],
        faculty: [{
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Faculty Name",
          designation: "Head of the Department",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        }],
        friends: [{
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Friend Name",
          year: "3rd Year Section A",
          group: "Information Technology",
          institute: "D Y patil College of Engineering"
        }]
      }
    },

    components: {
      CardImg3,
      CardImg
    }


  }
</script>