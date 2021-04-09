<template>
  <b-col>
    <b-row class="tab-row">
      <b-button @click="activeTab='Connections'" class="tab-button no-outline-button"
        v-bind:class="{'active-tab shadow': activeTab=='Connections'}">Connections</b-button>
      <b-button @click="activeTab='Group'" class="tab-button no-outline-button"
        v-bind:class="{'active-tab shadow': activeTab=='Group'}">Group</b-button>
    </b-row>

    <b-row v-if="activeTab=='Connections'">
      <b-col lg="8">
        <h1 class="title">All your connections</h1>
        <b-row v-for="friend in friends" :key="friend" class="comp">
          <b-col cols="8">
            <CardImg3 styles="margin-top: -1em" :src="friend.src" :name="friend.name" :sub1="friend.year"
              :sub2="friend.group" :sub3="friend.institute" />
          </b-col>
          <b-col class="gone" cols="4">
            <b-button class="button faculty-button" variant="info">View Profile
            </b-button>
          </b-col>
        </b-row>
      </b-col>
      <b-col style="padding: 0" lg="4">
        <h1 class="title">Pending Connections</h1>
        <div class="comp req-div">
          <b-row v-for="friend in friends" :key="friend">
            <b-col cols="3">
              <CardImg className="req" :src="friend.src" />
            </b-col>
            <b-col class="gone" cols="8">
              <b-button class="button req-btn" variant="info">Accept
              </b-button>
              <b-button class="req-btn" variant="danger">Decline
              </b-button>
            </b-col>
          </b-row>
        </div>
      </b-col>
    </b-row>

    <b-row v-if="activeTab=='Group'">

      <b-col lg="8">
        <h1 class="title">All your groups</h1>
        <b-row v-for="group in groups" :key="group" class="comp">
          <b-col cols="8">
            <CardImg styles="margin-top: -1em" :src="group.src" :name="group.name" :sub1="group.desc"/>
          </b-col>
          <b-col class="gone" cols="4">
            <b-button class="button faculty-button" variant="info">View Group
            </b-button>
          </b-col>
        </b-row>
      </b-col>
      <b-col style="padding: 0" lg="4">
        <h1 class="title">Create a group</h1>

        <b-row class="comp">
          <h1 class="title">Groups Created</h1>
          <b-button @click="groupCreateModal=true" class="button create-btn">+ Create Group</b-button>
        </b-row>
      </b-col>





      <div v-if="groupCreateModal">
        <div class="modal-mask createpostModal">
          <div class="modal-wrapper ">
            <div class="modal-dialog">
              <div class="modal-content">
                <b-icon @click="groupCreateModal=false" class="exit-modal" icon="x"></b-icon>

                <div class="modal-title-div">
                  <h1 class="modal-title shadow-none"><i class="far fa-edit"></i> Create new event</h1>
                </div>
                <b-form>
                  <b-form-group>
                    <b-form-input class="modal-input" type="text" placeholder="Group Name">
                    </b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="modal-input" type="text" placeholder="Description"></b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="modal-input" type="text"
                      placeholder="This needs to be a multi select form for friends"></b-form-input>
                  </b-form-group>
                  <b-button style="margin-left: 70%" class="post-btn button" @click="groupCreateModal=false">
                    Create
                  </b-button>
                </b-form>
              </div>
            </div>
          </div>
        </div>
      </div>
    </b-row>



  </b-col>

</template>


<style scoped>
  .title {
    padding: 1em 1em 0;
    font-size: 2em;
    font-weight: bold;
  }

  .req-btn {
    width: 40%;
    font-size: 1em;
    margin: 1.5em 0.5em 0;
  }

  .req-div {
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

  .create-btn {
    height: fit-content;
    padding: 0.5em;
    font-size: 1em;
    border-radius: 0.5em;
    margin: 1em 2em;
    margin-left: auto;
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


  .tab-button:hover {
    color: white !important;
    background-color: rgb(148, 148, 148) !important;
    box-shadow: none !important;
    border-radius: 0.5em;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
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
    cursor: pointer;
  }




  @media (max-width: 768px) {}
</style>

<style>
  .multiselect>.d-flex>input {
    background-color: #EAFDFB;

  }
</style>


<script>
  import CardImg3 from './Card-Img-3';
  import CardImg from './Card-Img';

  export default {
    data() {
      return {
        activeTab: "Connections",
        groupCreateModal: false,
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
          }
        ],
        groups: [{
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Group 1",
            desc: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet mauris sit amet lacus aliquet, nec varius ligula laoreet. Cras at felis ex"
          },
          {
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Group 2",
            desc: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet mauris sit amet lacus aliquet, nec varius ligula laoreet. Cras at felis ex"
          },
          {
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Group 3",
            desc: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet mauris sit amet lacus aliquet, nec varius ligula laoreet. Cras at felis ex"
          },
          {
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Group 4",
            desc: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet mauris sit amet lacus aliquet, nec varius ligula laoreet. Cras at felis ex"
          },
          {
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Group 5",
            desc: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet mauris sit amet lacus aliquet, nec varius ligula laoreet. Cras at felis ex"
          },
          {
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Group 6",
            desc: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam imperdiet mauris sit amet lacus aliquet, nec varius ligula laoreet. Cras at felis ex"
          }
        ],
        allFriends: ["Friend 1", "Friend 2", "Friend 3", "Friend 4", "Friend 5", "Friend 6"]
      }
    },

    components: {
      CardImg3,
      CardImg
    }


  }
</script>