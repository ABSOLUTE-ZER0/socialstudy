<template>
  <div class="main-div">
    <b-container fluid>
      <b-img class="cover-img" fluid src="https://placekitten.com/1000/300"></b-img>
      <b-row>
        <b-col cols="4">
          <b-row>
            <div class="group">
              <b-button @click="activeGroup=group" variant="outline-info" class="group-btn" v-for="group in groups"
                :key="group"> {{group}}
              </b-button>
            </div>
          </b-row>


        </b-col>
        <b-col cols="8">
          <b-row>
            <b-button @click="activeTab='About'" class="tab-button" variant="outline-primary">About</b-button>
            <b-button @click="activeTab='Subject'" class="tab-button" variant="outline-primary">Subject
            </b-button>
            <b-button @click="activeTab='Event'" class="tab-button" variant="outline-primary">Event
            </b-button>
            <b-button @click="activeTab='People'" class="tab-button" variant="outline-primary">People
            </b-button>
          </b-row>




          <div v-on="item = groupFilter">


            <div v-if="activeTab=='About'">
              <b-row style="margin-top: 0" class="comp">
                <p class="about"> {{item.about}} </p>
              </b-row>
            </div>


            <div v-if="activeTab=='Subject'">
              <b-row v-for="sub in item.subject" :key="sub" class="comp">
                <b-col cols="6">
                  <b-card class="subject-card" img-left :img-src="sub.src">
                    <b-card-body class="subject-body">
                      <b-card-title> {{sub.name}} </b-card-title>
                      <b-card-sub-title class="mb-2"> {{sub.year}} </b-card-sub-title>
                    </b-card-body>
                  </b-card>
                </b-col>
                <b-col cols="6">
                  <b-button @click="activeGroup='Event'" class="subject-button" variant="outline-primary">Study Material
                  </b-button>
                  <b-button @click="activeGroup='People'" class="subject-button" variant="outline-primary">Syllabus
                  </b-button>
                </b-col>
              </b-row>
            </div>




            <div v-if="activeTab=='Event'">
              <b-row v-for="event in item.events" :key="event" class="comp">
                <div class="event">
                  <b-col cols="2">
                    <p class="event-class">{{ event.date.split(" ")[0] }}</p>
                    <p style="font-size: 1.5em" class="event-class">{{ event.date.split(" ")[1] }}</p>
                  </b-col>
                  <b-col cols="7">
                    <h2 style="margin-top: 0.5em">{{ event.name }} </h2>
                    <h5>{{ event.type }}</h5>
                  </b-col>
                  <b-col cols="2">
                    <b-button variant="info" class="event-button">Register</b-button>
                  </b-col>
                </div>
              </b-row>
            </div>




            <div v-if="activeTab=='People'">
              <b-row v-for="people in item.persons" :key="people" class="comp">
                <b-col cols="8">
                  <b-card class="people-card" img-left :img-src="people.src">
                    <b-card-body style="margin-top:-1em" class="people-body">
                      <b-card-title> {{people.name}} </b-card-title>
                      <b-card-sub-title class="mb-2"> {{people.year}} | {{people.group}}</b-card-sub-title>
                      <b-card-sub-title class="mb-2"> {{people.institute}} </b-card-sub-title>
                    </b-card-body>
                  </b-card>
                </b-col>
                <b-col cols="4">
                  <b-button @click="activeGroup='People'" class="people-button" variant="outline-primary">Syllabus
                  </b-button>
                </b-col>
              </b-row>
            </div>





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


  .cover-img {
    width: 100%;
    max-height: 25rem !important;
    min-height: 25rem !important;
    border-radius: 1em;
  }

  .group {
    margin: 2em 1em;
    width: 100%;
  }

  .group-btn {
    width: 80%;
    padding: 1em;
    margin: 1em;
    border: 3px solid rgb(0, 174, 255);
  }


  .tab-button {
    margin: 1em 0.5em;
    border-radius: 0.5em;
    font-size: 2em;
    width: 20%;
  }

  .subject-button {
    margin: 2em 0.5em;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 40%;
  }

  .about {
    min-height: 10em;
    margin: 1em 2em 0
  }


  .subject-card {
    margin: 1em 2em 0;
    border: 0;
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



  .event {
    width: 100%;
    margin: 2em;
    display: flex;
  }

  .event-class {
    color: rgb(128, 128, 128);
    font-weight: bold;
    text-align: center;
    font-size: 2em;
    margin-left: -50%;
  }

  .event-button {
    width: 20em;
    margin-top: 2em;
  }


  .people-card {
    margin: 1em 2em 0;
    border: 0;
    width: 100%;
    border-radius: 0;
  }


  .people-button {
    margin: 2.5em 0.5em 0;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 80%;
  }
</style>


<script>
  export default {
    data() {
      return {
        activeGroup: "Information Technology",
        activeTab: "About",
        groups: ['Information Technology', 'Computer Science', 'Civil Engineering', 'E&TC', 'Mechanical Engineering'],
        items: [{
            name: "Information Technology",
            content: {
              about: "Some text describing the subject i guess?",
              subject: [{
                  src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
                  name: "Data Structures & Algorithm",
                  year: "3rd Semester"
                },
                {
                  src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
                  name: "Data Structures & Algorithm",
                  year: "3rd Semester"
                }

              ],
              events: [{
                date: "Dec 10",
                name: "Campus Placement Drive Infosys",
                type: "Campus Placement"
              }],
              persons: [{
                src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
                name: "Friend Name",
                year: "3rd Year Section A",
                group: "Information Technology",
                institute: "D Y patil College of Engineering"
              }]
            }
          },

          {
            name: "Computer Science",
            content: {
              about: "Some text asdhtrfyujfndhbgfsdfsvdb sgthhjmnbv describing the subject i guess?",
              subject: [{
                src: "",
                name: "",
                year: ""
              }],
              events: [{
                date: "",
                name: "",
                type: ""
              }],
              persons: [{
                src: "",
                name: "",
                year: "",
                group: "",
                institute: ""
              }]
            }
          }
        ]
      }

    },
    computed: {
      groupFilter: function () {
        var final;
        this.items.forEach(item => {
          if (item.name == this.activeGroup) {
            final = item;
          } else {
            final = this.items[0]
          }
        });
        return final.content;
      },
    }
  }
</script>