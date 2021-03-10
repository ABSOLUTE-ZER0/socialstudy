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
            <b-button @click="activeTab='Subject'" class="tab-button" variant="outline-primary">Subject</b-button>
            <b-button @click="activeTab='Event'" class="tab-button" variant="outline-primary">Event</b-button>
            <b-button @click="activeTab='People'" class="tab-button" variant="outline-primary">People</b-button>
          </b-row>

          <div v-on="item = groupFilter">

            <div v-if="activeTab=='About'">
              <b-row style="margin-top: 0" class="comp">
                <p class="about"> {{item.about}} </p>
              </b-row>
            </div>

            <div v-if="activeTab=='Subject'">
              <b-row v-for="sub in item.subject" :key="sub" class="comp">
                <b-col md="6" cols="12">
                  <CardImg :src="sub.src" :name="sub.name" :sub1="sub.year" />
                </b-col>
                <b-col md="6" cols="12">
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
                    <b-col cols="3">
                      <p class="event-date">{{ event.date.split(" ")[0] }}</p>
                      <p style="font-size: 1.5em" class="event-date">{{ event.date.split(" ")[1] }}</p>
                    </b-col>
                    <b-col md="6" cols="9">
                      <h2 class="event-title" style="margin-top: 0.5em">{{ event.name }} </h2>
                      <h5 class="event-sub"> {{ event.type }}</h5>
                    </b-col>
                    <b-col class="gone" md="3" cols="12">
                      <b-button variant="info" class="event-button">Register</b-button>
                    </b-col>
                </div>
              </b-row>
            </div>

            <div v-if="activeTab=='People'">
              <b-row v-for="people in item.persons" :key="people" class="comp">
                <b-col style="padding-left:0" md="8" cols="12">
                  <CardImg3 styles="margin-top: -1em" :src="people.src" :name="people.name" :sub1="people.year"
                    :sub2="people.group" :sub3="people.institute" />
                </b-col>
                <b-col class="gone" md="4" cols="12">
                  <b-button class="people-button" variant="outline-primary">View Profile
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
    font-size: 1.5em;
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



  .event {
    width: 100%;
    margin: 2em;
    display: flex;
  }

  .event-date {
    color: rgb(128, 128, 128);
    font-weight: bold;
    text-align: center;
    font-size: 2em;
    margin-left: -50%;
  }

  .event-button {
    width: 100%;
    margin-top: 2em;
  }


  .people-button {
    margin: 2.5em 0.5em 0;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 80%;
  }

  @media (max-width: 768px) {

    .cover-img {
      width: 100%;
      max-height: 18em !important;
      min-height: 18em !important;
      border-radius: 1em;
    }

    .tab-button {
      margin: 1em 0.5em;
      font-size: 1.1em;
    }

    .group-btn {
      width: 80%;
      padding: 1em;
      margin: 1em;
      border: 3px solid rgb(0, 174, 255);
      font-size: 1.2em;
    }

    .subject-button {
      margin: 0.5em;
      border-radius: 0.5em;
      font-size: 1em;
      width: 100%;
    }


    .event {
      width: 100%;
      margin: 1em;
      display: flex;
    }

    .event-date {
      color: rgb(128, 128, 128);
      font-weight: bold;
      text-align: center;
      font-size: 2em;
      margin-left: -50%;
      margin-bottom: 0;
    }

    .event-title{
      font-size: 1.2em;
      font-weight: bolder;
    }

    .event-sub{
      font-size: 1.1em;
    }



    .gone {
      display: none;
    }


  }
</style>


<script>
  import CardImg from "./Card-Img"
  import CardImg3 from "./Card-Img-3"
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
    },
    components: {
      CardImg,
      CardImg3
    }
  }
</script>