<template>
  <div>
    <b-row style="padding: 1em" class="comp">
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
    <b-row class="comp">
      <b-col>
        <b-row>
          <h4 style="margin: 2em; font-weight: bold; margin-bottom: 0;margin-top: 1em;">Tools</h4>
        </b-row>

        <b-row>
          <Navitem v-on:changeSite="updateSite($event);changePage()" :items="navitems1" />
        </b-row>

        <b-row>
          <Navitem v-on:changeSite="updateSite($event);changePage()" :items="navitems2" />
        </b-row>

        <b-row>
          <Navitem v-on:changeSite="updateSite($event);changePage()" :items="navitems3" />
        </b-row>
      </b-col>
    </b-row>

  </div>

</template>


<style scoped>
  .tools-img {
    min-width: 8em;
    margin: 1em 3em !important;
    border: 0;
    text-align: center;
  }

  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  .tool {
    text-align: center;
    margin: 1em 2em;
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