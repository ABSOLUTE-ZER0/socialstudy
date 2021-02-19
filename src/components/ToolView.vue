<template>

  <div>

    <div class="comp" v-if="pageName=='StartLiveClass'">
      <b-row>
        <b-col cols="9">
          <b-button style="margin-left: 10%" class="con-group-btn" variant="outline-info">Start Live Class</b-button>
          <b-button class="con-group-btn" variant="info">+ Create Group</b-button>
        </b-col>
        <b-col cols="3">
          <b-navbar>
            <b-navbar-nav>
              <b-nav-item class="filter">
                <i class="fas fa-2x icon fa-clipboard-check"></i> Select Filter
              </b-nav-item>
            </b-navbar-nav>
          </b-navbar>
        </b-col>
      </b-row>
      <b-row>
        <p style="margin-left: 10%">Select group to start live classes</p>
        <p style="margin-left: 10%">Below active background is not a bug ,once you give different id's for different
          sections it will work properly</p>
      </b-row>
    </div>



    <div class="comp" v-if="pageName=='FileSharing'">
      <b-row>
        <b-col cols="9">
          <b-button style="margin-left: 10%" class="con-group-btn" variant="outline-info">+ Upload File</b-button>
          <b-button class="con-group-btn" variant="info">+ Create Group</b-button>
        </b-col>
        <b-col cols="3">
          <b-navbar>
            <b-navbar-nav>
              <b-nav-item class="filter">
                <i class="fas fa-2x icon fa-clipboard-check"></i> Select Filter
              </b-nav-item>
            </b-navbar-nav>
          </b-navbar>
        </b-col>
      </b-row>
      <b-row>
        <p style="margin-left: 10%">Select group to start live classes</p>
        <p style="margin-left: 10%">Below active background is not a bug ,once you give different id's for different
          sections it will work properly</p>
      </b-row>
    </div>

    <div v-if="pageName=='Assignment'">
      <div class="comp">
        <b-row>
          <b-col cols="9">
            <b-button style="margin-left: 10%" class="con-group-btn" variant="outline-info">+ Create Assignment
            </b-button>
          </b-col>
          <b-col cols="3">
            <b-navbar>
              <b-navbar-nav>
                <b-nav-item class="filter">
                  <i class="fas fa-2x icon fa-clipboard-check"></i> Select Filter
                </b-nav-item>
              </b-navbar-nav>
            </b-navbar>
          </b-col>
        </b-row>
        <b-row>
          <p style="margin-left: 10%">Select group to start live classes</p>
          <p style="margin-left: 10%">Below active background is not a bug ,once you give different id's for different
            sections it will work properly</p>
        </b-row>
      </div>

        <div v-for="item in items" :key="item" class="comp">
        <b-row >
          <b-col cols="8">
            <CardImg3 :src="item.src" :name="item.name" :sub2="item.subject" :sub1="item.group" />
          </b-col>
          <b-col cols="4">
            <b-button class="assignment-button" variant="info">Edit
            </b-button>
            <b-button class="assignment-button" variant="danger">Delete
            </b-button>
          </b-col>
        </b-row>
        </div>

      </div>






    <div class="comp" v-if="pageName=='StartLiveClass' || pageName=='FileSharing' || pageName=='ManageGroup'">
      <SetSection />
    </div>



  </div>

</template>


<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
    white-space: pre-wrap;
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
    font-size: 2em;
  }

  
  .assignment-button {
    margin: 2.5em 1em;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 40%;
  }

  .con-group-btn {
    margin: 1.5em;
    width: 30%;
    border-radius: 1em;
    font-size: 2em;
  }
</style>



<script>
  import SetSection from "./SetSection"
  import CardImg3 from "./Card-Img-3"
  export default {
    data() {
      return {
        siteName: "",
        items: [{
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Sample Assignment 1",
            group: "Assigned group",
            subject: "Subject",
          },
          {
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Sample Assignment 2",
            group: "Assigned group",
            subject: "Subject",
          }
        ]
      }
    },
    components: {
      SetSection,
      CardImg3
    },
    methods: {

    },
    props: {
      pageName: String
    }
  }
</script>