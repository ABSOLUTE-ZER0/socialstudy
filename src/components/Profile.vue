<template>
  <div class="main-div">
    <b-container fluid>
      <div>
        <b-img class="cover-img" fluid src="https://placekitten.com/1000/300"></b-img>
        <b-img class="profile-img" fluid src="https://placekitten.com/1000/300" rounded="circle" alt="Circle image">
        </b-img>
      </div>

      <b-row>
        <b-col md="4" cols="12">
          <b-row style="margin-top: 6em;" class="comp">
            <div class="desc">
              <h2 class="profile-title">Name</h2>
              <p class="profile-details">Year, Branch</p>
              <p class="profile-details">College Name</p>
              <p class="profile-details">Location</p>
            </div>
            <div class="desc2">
              <h2 class="profile-title" style="text-align: left;">Description</h2>
              <p style="text-align: left;">Some detailed Description</p>
            </div>
          </b-row>


        </b-col>
        <b-col cols="12" md="8">

          <StartPost />
          <b-row>
            <b-button @click="academics=true;posts=false" style="  margin-left: 7em;" class="profile-button"
              variant="outline-primary">Academics</b-button>
            <b-button @click="posts=true;academics=false;" class="profile-button" variant="outline-primary">Posts
            </b-button>
          </b-row>
          <div v-if="academics">
            <b-row class="comp">
              <h2 class="profile-title" style="margin: 1em 2em 0;width:100%"> Education </h2>
              <b-table style="margin: 2em" striped hover :items="education" :fields="fields"></b-table>
            </b-row>
            <b-row class="comp">
              <div style="width:80%">
                <h2 class="profile-title" style="margin: 1em 2em 0; width:100%"> Certification & Achievements </h2>

                <div style="border-top: 1.5px solid rgba(128, 128, 128, 0.568); margin:1em" v-for="item in certificate"
                  :key="item">
                  <CardImg3 margin="3em !important" :src="item.src" :name="item.name" :sub1="item.year"
                    :sub2="item.institute" />
                </div>

              </div>
            </b-row>
            <b-row class="comp">
              <h2 class="profile-title" style="margin: 1em 2em 0;width:100%"> Report Cards </h2>
              <div v-for="item in report" :key="item" class="report">
                <b-col cols="2">
                  <p class="report-class">{{ item.class.split(" ")[0] }}</p>
                  <p class="report-class">{{ item.class.split(" ")[1] }}</p>
                </b-col>
                <b-col cols="6">
                  <h2 class="report-title">{{ item.name}}</h2>
                  <h5 class="report-desc">{{item.institute}}</h5>
                </b-col>
                <b-col class="gone" cols="4">
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
  .main-div {
    max-width: 100%;
    margin: 1em;
  }

  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  .desc,
  .desc2 {
    padding: 2em;
    text-align: center;
    width: 100%;

  }

  .cover-img {
    width: 100%;
    max-height: 400px !important;
    min-height: 400px !important;
    border: 3px solid rgb(0, 183, 255);
    border-radius: 2em;
    background-color: rgb(0, 183, 255);
  }

  .profile-img {
    position: absolute;
    left: 160px;
    top: 450px;
    width: 160px;
    height: 160px;
    background-color: rgb(0, 183, 255);
    border: 3px solid rgb(0, 183, 255);

  }

  .profile-button {
    width: 20%;
    margin: 1em;
  }

  .certificate-card {
    margin: 1em 2em 0;
    border: 0;
    border-top: 2.5px solid rgba(128, 128, 128, 0.568);
    width: 100%;
    border-radius: 0;
  }

  .card-img-left {
    border: 0;
    width: 5em;
    height: 5em;
    margin-top: 1.5em;
    border-radius: 50%;
  }

  .report {
    width: 100%;
    margin: 2em;
    display: flex;
  }

  .report-class {
    color: rgb(128, 128, 128);
    font-weight: bold;
    text-align: center;
    font-size: 1.3em;
    margin-left: -50%;
  }

  .report-button {
    width: 10em;
    margin-top: 1em;
  }

  @media (max-width: 1000px) and (min-width: 768px) {
    .profile-img {
      left: 100px;
      top: 450px;
      width: 160px;
      height: 160px;
    }
  }

  @media (max-width: 768px) {

    .cover-img {
      width: 100%;
      max-height: 18em !important;
      min-height: 18em !important;
      border-radius: 1em;
    }

    .profile-img {
      left: 5em;
      top: 23em;
      width: 5rem;
      height: 5rem;
    }

    .profile-title {
      font-size: 2em;
      width: 30%;
    }

    .profile-details {
      margin: 0 !important;
    }

    .desc {
      padding: 1em 2em;
      text-align: left;
      width: 40%;

    }

    .desc2 {
      width: 50%;
      padding: 1em 2em;

    }

    .profile-button {
      width: 40%;
      margin: 0.5em 0;
      margin-left: 2.5em !important;
      font-size: 1.2em;
    }

    .report-class {
      color: rgb(128, 128, 128);
      font-size: 1.5em;
      margin-bottom: 0;
    }


    .gone {
      display: none;
    }

    .report-title {
      font-size: 1.5em;
      margin-top: 0.2em;
    }

    .report-desc {
      font-size: 1.2em;
    }

  }
</style>


<script>
  import StartPost from "./StartPost"
  import CardImg3 from "./Card-Img-3"
  export default {
    data() {
      return {
        academics: true,
        posts: false,
        fields: ['Category', 'Institute', 'Class', 'Year', 'Marks'],
        education: [{
            isActive: true,
            Category: "School, ICSE",
            Institute: 'Don Bosco',
            Class: "10",
            Year: '2009',
            Marks: '84%'
          },
          {
            isActive: true,
            Category: "School, CBSE",
            Institute: 'D.A.V Public',
            Class: "12",
            Year: '2011',
            Marks: '86%'
          }
        ],
        certificate: [{
            src: "https://placekitten.com/300/300",
            name: "Passing Certificate",
            year: "Class 10",
            institute: "Don Bosco Academy"
          },
          {
            src: "https://placekitten.com/300/300",
            name: "Passing Certificate",
            year: "Class 10",
            institute: "Don Bosco Academy"
          }

        ],
        report: [{
          class: "Class 8",
          name: "Report Card",
          institute: "Don Bosco Academy"
        }]
      }
    },
    components: {
      StartPost,
      CardImg3
    }
  }
</script>