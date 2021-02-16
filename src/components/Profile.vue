<template>
  <div class="main-div">
    <b-container fluid>
      <b-img class="cover-img" fluid src="https://placekitten.com/1000/300" ></b-img>
      <b-img class="profile-img" fluid src="https://placekitten.com/1000/300" rounded="circle" alt="Circle image"></b-img>
      <b-row>
      <b-col cols="4">
      <b-row style="margin-top: 6em;" class="comp">
        <div class="desc">
          <h2 class="profile-name">Name</h2>
          <p>Year, Branch</p>
          <p>College Name</p>
          <p>Location</p>
          <h2  style="text-align: left;">Description</h2>
          <p style="text-align: left;">Some detailed Description</p>
        </div>
      </b-row>


      </b-col>
      <b-col cols="8">

        <StartPost />
        <b-row>
          <b-button @click="academics=true;posts=false" style="  margin-left: 7em;" class="profile-button" variant="outline-primary">Academics</b-button>
          <b-button @click="posts=true;academics=false;" class="profile-button" variant="outline-primary">Posts</b-button>
        </b-row>
        <div v-if="academics">
        <b-row class="comp">
          <h2 style="margin: 1em 2em 0"> Education </h2>
            <b-table style="margin: 2em" striped hover :items="education" :fields="fields"></b-table>
        </b-row>
        <b-row class="comp">
          <div style="width:80%">
          <h2 style="margin: 1em 2em 0"> Certification & Achievements </h2>
            <b-card v-for="item in certificate" :key="item" class="certificate-card" img-left :img-src="item.src">
              <b-card-body class="certificate-body">
                <b-card-title> {{ item.name }} </b-card-title>
                <b-card-sub-title class="mb-2"> {{ item.year }} | {{ item.institute }} </b-card-sub-title>
              </b-card-body>
            </b-card>   
          </div>
        </b-row>
        <b-row class="comp">
          <h2 style="margin: 1em 2em 0"> Report Cards </h2>
          <div v-for="item in report" :key="item" class="report">
          <b-col cols="2">
            <p class="report-class">{{ item.class.split(" ")[0] }}</p>
            <p class="report-class">{{ item.class.split(" ")[1] }}</p>
          </b-col>
          <b-col cols="6">
            <h2>{{ item.name}}</h2>
            <h5>{{item.institute}}</h5>
          </b-col>
          <b-col cols="4">
            <b-button variant="info" class="report-button">View</b-button>
          </b-col>
          </div>
        </b-row>
        </div>
      </b-col>
      </b-row>
    </b-container>

  </div>
</template>


<style scoped>

.main-div{
  max-width: 100%;
  margin: 1em;
}
    .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

.desc{
  padding: 2em;
  text-align: center;
  width: 100%;
  
}
.cover-img{
  width: 100%;
  max-height: 25rem !important;
  min-height: 25rem !important;
  border: 3px solid rgb(0, 183, 255);
  border-radius: 2em;
  background-color: rgb(0, 183, 255);
}


.profile-img{
  position: absolute;
  left: 15em;
  top: 30rem;
  width: 10rem;
  height: 10rem;
  background-color: rgb(0, 183, 255);
  border: 3px solid rgb(0, 183, 255);

}

.profile-button{
  width: 20%;
  margin: 1em;
}

.certificate-card{
  margin: 1em 2em 0;
  border: 0;
  border-top: 2.5px solid rgba(128, 128, 128, 0.568);
  width: 100%;
  border-radius: 0;
}
.card-img-left{
  border: 0;
  width: 5em;
  height: 5em;
  margin-top: 1.5em;
  border-radius: 50%;
}

.report{
  width: 100%;
  margin: 2em;
  display: flex;
}

.report-class{
  color: rgb(128, 128, 128);
  font-weight: bold;
  text-align: center;
  font-size: 1.3em;
  margin-left: -50%;
}

.report-button{
  width: 10em;
  margin-top: 1em;
}

@media (max-width: 1000px) {
.profile-img{
  left: 5em;
  top: 30em;
  width: 10rem;
  height: 10rem;
}
}

</style>


<script>
import StartPost from "./StartPost"
  export default {
    data() {
      return {
        academics: true,
        posts: false,
        fields: ['Category', 'Institute','Class', 'Year', 'Marks'],
        education: [
          { isActive: true, Category: "School, ICSE", Institute: 'Don Bosco', Class: "10", Year: '2009', Marks: '84%' },
          { isActive: true, Category: "School, CBSE", Institute: 'D.A.V Public', Class: "12",Year:'2011', Marks: '86%' }
        ],
        certificate: [
          {src: "https://placekitten.com/300/300", name: "Passing Certificate", year: "Class 10", institute: "Don Bosco Academy"},
          {src: "https://placekitten.com/300/300", name: "Passing Certificate", year: "Class 10", institute: "Don Bosco Academy"}

        ],
        report: [
          {class: "Class 8", name: "Report Card", institute: "Don Bosco Academy"}
        ]
      }
    },
    components: {
      StartPost
    }
  }
</script>