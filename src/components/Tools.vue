<template>
  <b-row ref="sticky" class="comp tool-div">
    <div class="title-div">
      <h1 class="d-none d-lg-block title">Tools</h1>

    </div>

    <b-card-group class="tool-card-div" deck>
      <b-card class="tool-card">
        <template class="tool-row">
          <Navitem v-on:changeSite="updateSite($event);changePage()" :items="navitems1" :active="pageName" />
        </template>
      </b-card>

      <b-card class="tool-card">
        <template class="tool-row">
          <Navitem v-on:changeSite="updateSite($event);changePage()" :items="navitems2" :active="pageName" />
        </template>
      </b-card>

      <b-card class="tool-card">
        <template class="tool-row">
          <Navitem v-on:changeSite="updateSite($event);changePage()" :items="navitems3" :active="pageName" />
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

  .title-div {
    border-bottom: 1.5px solid rgba(0, 0, 0, 0.274);
    width: 100%;
  }

  .title {
    font-size: 1.5em;
    font-weight: bold;
    margin: 20px 20px 10px;
    text-transform: uppercase;
  }

  .navitem {
    flex: 1;
  }

  .tool-row {
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
            imgclass: "fas icon fa-video",
            color: "color:#df4949"
          },
          {
            name: "File Sharing",
            pageName: "FileSharing",
            imgclass: "fas icon fa-folder",
            color: "color:#7a75ff"
          },

        ],
        navitems2: [{
            name: "Assignment",
            pageName: "Assignment",
            imgclass: "fas icon fa-clipboard-check",
            color: "color:#2bd5a9"
          }, {
            name: "Manage Group",
            pageName: "ManageGroup",
            imgclass: "fas icon fa-users",
            color: "color:#efd74f"
          },

        ],
        navitems3: [{
            name: "Attendance",
            pageName: "Attendance",
            imgclass: "fas icon fa-clipboard-list",
            color: "color:#6c757d"
          },
          {
            name: "Report Card",
            pageName: "ReportCard",
            imgclass: "fas icon fa-file-alt",
            color: "color:#ffcd51"
          },
        ],
        pageName: "",
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
    },
    mounted() {

      this.$nextTick(function () {

        var distanceFromTop = this.$refs.sticky.scrollTop;
        
        if (distanceFromTop >= this.$refs.sticky.clientHeight) {
          this.$refs.sticky.classList.add('fixed')

        } else {
          document.getElementById("sticky").classList.remove('fixed')
        }
      })



    }

  }
</script>