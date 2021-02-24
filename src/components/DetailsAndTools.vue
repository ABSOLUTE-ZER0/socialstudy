<template>
  <div>
    <b-row style="padding: 1em" class="comp gone">
      <b-col style="text-align: center; margin-right: 2em" cols="12" md="auto">
        <b-row>
          <b-img style="margin-bottom: 1em" v-bind="mainProps" rounded="circle" alt="Circle image"></b-img>
        </b-row>
        <b-button variant="link" @click="pageName='MyProfile';changePage()">My Profile </b-button>
      </b-col>
      <b-col>
        <p>Name</p>
        <p>Institution</p>
        <p>Year and Branch</p>
        <p>Position</p>
      </b-col>
    </b-row>
    <b-row class="comp tool-div">
      <b-card-group class="tool-card-div" deck>
        <b-card class="tool-card">
          <template class="tool-row">
            <Navitem v-on:changeSite="updateSite($event);changePage()" :items="navitems1" />
          </template>
        </b-card>

        <b-card class="tool-card">
          <template class="tool-row">
            <Navitem v-on:changeSite="updateSite($event);changePage()" :items="navitems2" />
          </template>
        </b-card>

        <b-card class="tool-card">
          <template class="tool-row">
            <Navitem v-on:changeSite="updateSite($event);changePage()" :items="navitems3" />
          </template>
        </b-card>
      </b-card-group>
    </b-row>

  </div>

</template>


<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  .tool-card-div {
    display: block;

  }

  .navitem{
    width: 50%;
  }

    .card-body {
      padding: -15px;
    }
    
  .tool-card {
    border: 0;
    max-width: 100%;
    border-radius: 2em;
  }


  @media (max-width: 768px) {
    .tool-row {
      width: 30%;
      font-size: 0.5em;
    }

    .tool-div {
      border-radius: 2em;
      margin-bottom: 0 !important;
    }

    .tool-col {
      background-color: white !important;
      border-radius: 2em;
      margin: 1em;
      display: flex;
    }

    .tool-card-div {
      display: flex;
    }

    .tool-card {
      border: 0;
      max-width: 100%;
      font-size: 0.6em;
      border-radius: 2em;
      margin-bottom: 0 !important;
    }

    .card-body {
      padding: 0;
    }

    .navbar-div {
      padding: 0;
      margin-top: 0 !important;

    }


    .gone {
      display: none;
    }
  }
</style>







<script>
  import Navitem from "./Navitem"
  export default {
    data() {
      return {
        navitems1: [{
            name: "Start Live Class",
            pageName: "StartLiveClass",
            imgclass: "fas fa-4x icon fa-video"
          },
          {
            name: "File Sharing",
            pageName: "FileSharing",
            imgclass: "fas fa-4x icon fa-folder"
          },

        ],
        navitems2: [{
            name: "Assignment",
            pageName: "Assignment",
            imgclass: "fas fa-4x icon fa-clipboard-check"
          }, {
            name: "Manage Group",
            pageName: "ManageGroup",
            imgclass: "fas fa-4x icon fa-users"
          },

        ],
        navitems3: [{
            name: "Attendance",
            pageName: "Attendance",
            imgclass: "fas fa-4x icon fa-clipboard-list"
          },
          {
            name: "Report Card",
            pageName: "ReportCard",
            imgclass: "fas fa-4x icon fa-file-alt"
          },
        ],
        pageName: "MyProfile",
        mainProps: {
          src: "https://placekitten.com/1000/300",
          width: 130,
          height: 130,
          class: 'profile-img'
        }
      }
    },
    methods: {
      changePage: function () {
        this.$emit("changeSite", this.pageName)
      },
      updateSite(newValue) {
        this.pageName = newValue;
      }
    },
    components: {
      Navitem
    }

  }
</script>