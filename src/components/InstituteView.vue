<template>
  <div class="main-div">
    <b-container fluid>
      <b-row style="margin:10px -15px !important" class="comp detail-row">
        <CardImg
          src="https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg"
          name="Bachelor of Technology" sub1="Under Graduate Degree" sub2="4 Year" />
        <b-button v-if="isAdmin" class="button edit-btn">Edit</b-button>
      </b-row>
      <b-row>
        <b-col cols="3">
          <b-row>
            <div class="group comp">
              <b-button @click="activeGroup=group" class="group-btn" v-for="group in groups"
                v-bind:class="{'active-group shadow': activeGroup==group}" :key="group"> {{group}}
              </b-button>
            </div>
          </b-row>
        </b-col>

        <b-col cols="9" style="padding-right:0">
          <b-row class="tab-row">
            <b-button @click="activeTab='About'" class="tab-button no-outline-button"
              v-bind:class="{'active-tab shadow': activeTab=='About'}">About</b-button>
            <b-button @click="activeTab='Subject'" class="tab-button no-outline-button"
              v-bind:class="{'active-tab shadow': activeTab=='Subject'}">Subject</b-button>
            <b-button @click="activeTab='Event'" class="tab-button no-outline-button"
              v-bind:class="{'active-tab shadow': activeTab=='Event'}">Event</b-button>
            <b-button @click="activeTab='People'" class="tab-button no-outline-button"
              v-bind:class="{'active-tab shadow': activeTab=='People'}">People</b-button>
          </b-row>

          <div v-on="item = groupFilter">

            <div v-if="activeTab=='About'">
              <b-row style="margin-top: 0" class="comp">
                <p class="about"> {{item.about}} </p>
                <b-button v-if="isAdmin" class="button edit-btn edit2">Edit</b-button>

              </b-row>
            </div>

            <div v-if="activeTab=='Subject'">
              <b-row style="text-align:right">
                <button v-if="isAdmin" @click="openModal()" class="add-sub">+ Add Subject</button>

              </b-row>
              <b-row v-for="sub in item.subject" :key="sub" class="comp">
                <b-col md="9">
                  <CardImg :src="sub.src" :name="sub.name" :sub1="sub.year" />
                </b-col>
                <b-col md="3">
                  <b-button @click="changePage()" class="button subject-button" variant="outline-primary">View
                  </b-button>
                </b-col>
              </b-row>

              <div v-if="subCreateModal">
                <div class="modal-mask createpostModal">
                  <div class="modal-wrapper ">
                    <div class="modal-dialog">
                      <div class="modal-content">
                        <b-icon @click="subCreateModal=false" class="exit-modal" icon="x"></b-icon>

                        <div class="modal-title-div">
                          <h1 class="modal-title shadow-none"><i class="far fa-edit"></i> Create new institute</h1>
                        </div>
                        <b-form>
                          <b-form-group>
                            <b-form-input class="modal-input" type="text" placeholder="Subject Name">
                            </b-form-input>
                          </b-form-group>
                          <b-form-group>
                            <b-form-input class="modal-input" type="text" placeholder="Year"></b-form-input>
                          </b-form-group>
                          <b-form-group>
                            <b-form-input class="modal-input" type="text" placeholder="Type(Theory/practical)">
                            </b-form-input>
                          </b-form-group>
                          <b-form-group>
                            <b-form-input class="modal-input" type="text" placeholder="Dsecription"></b-form-input>
                          </b-form-group>
                          <b-button style="margin-left: 70%" class="post-btn" @click="subCreateModal=false">Create
                          </b-button>
                        </b-form>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
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
                    <b-button variant="info" class="button event-button">Register</b-button>
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
                  <b-button class="button people-button" variant="outline-primary">Message
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


  .edit-btn {
    position: absolute;
    top: 4em;
    right: 8em;
    width: 10%;
    border-radius: 2em;
  }

  .edit2 {
    top: 6em;
  }


  .group {
    width: 100%;
    margin-left: 2em;
    border-radius: 0;
  }

  .group-btn {
    width: 100%;
    padding: 1em;
    color: #01C4C9 !important;
    background-color: rgb(255, 255, 255) !important;
    border-radius: 0;
    border: 0;
    text-transform: uppercase;
    font-weight: bold;
  }

  .tab-row {
    border-bottom: 2px solid rgb(117, 117, 117);
    margin-bottom: 1em;
    margin-left: 0;
    margin-right: 10px;
    display: flex;
  }


  .tab-button {
    margin: 0.5em 0 0;
    font-size: 1.5em;
    flex: 1;
    text-align: center;
    color: rgb(117, 117, 117) !important;
  }

  button.active-tab.tab-button {
    background-color: rgb(117, 117, 117) !important;
    color: white !important;
    border-radius: 0.5em;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
  }

  button.active-group.group-btn {
    background-color: #01C4C9 !important;
    color: white !important;
    border-radius: 0;

  }

  .group-btn:active,
  .group-btn:focus {
    color: initial;
    background-color: none;
    box-shadow: none !important;
  }

  .tab-button:hover {
    border-radius: 0.5em;
  }

  .group-btn:hover,
  .tab-button:hover {
    color: white !important;
    background-color: rgb(148, 148, 148) !important;
    box-shadow: none !important;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
  }

  .about {
    min-height: 10em;
    margin: 1em 2em 0
  }

  .add-sub {
    margin-left: auto;
    margin-right: 4em;
    font-size: 1.3em;
    border: 1px solid grey;
    padding: 0.5em 1em;
    border-radius: 1em;
  }



  .event {
    width: 100%;
    margin: 2em;
    display: flex;
  }

  .subject-button {
    margin: 2.5em 0.5em 0;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 80%;
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


  /* modal */
  .createpostModal {
    position: fixed;
    z-index: 200;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .5);
    display: table;
    transition: opacity .3s ease;
  }

  .modal-title-div {
    width: 100%;
    border-bottom: 1.5px solid #a8a8a86c;
  }

  .modal-title {
    color: #01C4C9;
    margin: 20px 5% 20px;
    font-size: 2em;
    text-shadow: 2px 1px 1px #01c2c980;
  }

  .modal-dialog {
    pointer-events: all !important;
    max-width: none !important;
    min-width: 100% !important;
    padding: 0 10%;
    margin: 0;
  }

  .modal-wrapper {
    display: table-cell;
    vertical-align: middle;

  }

  .modal-content {
    width: 60%;
    margin-left: 20%;
    border-radius: 1em;
  }


  .modal-input {
    background-color: #EAFDFB;
    border: 0;
    margin: 1em 5% 0;
    border-radius: 0.5em;
    font-size: 1.5em;
    width: 90%;
  }

  .post-btn {
    margin: 1em;
    width: 20%;
    background-color: #01C4C9;
    border: 0;
  }


  .exit-modal {
    color: red;
    font-size: 2.5em;
    position: absolute;
    top: 0.2em;
    right: 0.5em;
  }

  @media (max-width: 768px) {

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

    .event-title {
      font-size: 1.2em;
      font-weight: bolder;
    }

    .event-sub {
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
        view: false,
        subCreateModal: false,
        display: {},
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
    },
    methods: {
      openModal() {
        this.subCreateModal = true;
      },
      changePage(){
        this.$emit("subjectDetailsPage", "SubjectDetails")
      }
    },
    props: {
      isAdmin: Boolean
    }
  }
</script>