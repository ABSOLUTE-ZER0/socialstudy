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
  </div>

</template>


<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }



  @media (max-width: 768px) {
    .gone {
      display: none;
    }
  }
</style>







<script>
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


  }
</script>