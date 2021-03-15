<template>
      <b-row class="comp tool-div">
          <h1 class="d-none d-lg-block title">Tools</h1>

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
</template>


<style scoped>
  .tool-card-div {
    display: block;
    width: 100%;
  }

  .title{
    font-size: 2em;
    font-weight: bold;
    margin: 1em 1em 0;
  }

  .navitem{
    flex: 1;
  }

  .tool-row{
      width: 100%;

  }

      .card-body {
      padding: 0;
    }
    
  .tool-card {
    border: 0;
    width: 100%;
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
            imgclass: "fas fa-4x icon fa-video",
            color: "color:#df4949"
          },
          {
            name: "File Sharing",
            pageName: "FileSharing",
            imgclass: "fas fa-4x icon fa-folder",
            color: "color:#7a75ff"
          },

        ],
        navitems2: [{
            name: "Assignment",
            pageName: "Assignment",
            imgclass: "fas fa-4x icon fa-clipboard-check",
            color: "color:#2bd5a9"
          }, {
            name: "Manage Group",
            pageName: "ManageGroup",
            imgclass: "fas fa-4x icon fa-users",
            color: "color:#efd74f"
          },

        ],
        navitems3: [{
            name: "Attendance",
            pageName: "Attendance",
            imgclass: "fas fa-4x icon fa-clipboard-list",
            color: "color:#6c757d"
          },
          {
            name: "Report Card",
            pageName: "ReportCard",
            imgclass: "fas fa-4x icon fa-file-alt",
            color: "color:#ffcd51"
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