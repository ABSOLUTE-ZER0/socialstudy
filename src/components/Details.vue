<template>
  <div>
    <b-row class="comp gone">
      <b-col class="image-col" cols="12">
        <b-row @click="changePage()" class="image-div">
          <b-col md="5">
            <b-img class="image" v-bind="mainProps" rounded="circle" alt="Circle image"></b-img>
          </b-col>
          <b-col md="7" class="image-text-col gone-mid">
            <p>Name</p>
            <p>Position </p>
          </b-col>
        </b-row>
      </b-col>
      <b-col class="text-col" offset-md="5">
        <p class="show">Name</p>
        <p class="show">Position </p>
        <p>Institution</p>
        <p>Year and Branch</p>
      </b-col>
    </b-row>
  </div>

</template>


<style scoped>
  .image-col {
    padding: 20px;
    border-top-left-radius: 1em;
    border-top-right-radius: 1em;
    background: linear-gradient(to bottom, rgb(255, 255, 255) 30%, rgb(1, 196, 201) 30%, rgb(1, 196, 201) 70%, rgb(255, 255, 255) 70%);
  }

  .image {
    width: 110px;
    height: 110px;
    border: 5px solid white;
  }


  .image-div {
    cursor: pointer;
  }

  .image-text-col>p {
    color: white;
    font-size: 1.2em;
    font-weight: bold;
    margin: 0;
  }

  .image-text-col {
    margin-top: 30px;
  }

  .text-col {
    margin-top: -40px;
    margin-bottom: 10px;
  }

  .text-col>p {
    font-size: 1.1em;
    font-weight: bold;
    margin-bottom: 5px;
  }

  .show{
    display: none;
  }

  @media (max-width: 1500px) {
    .image {
      width: 90px;
      height: 90px;
      border: 3px solid white;
    }

    .image-text-col {
      margin-top: 20px;
    }

  }

  @media (max-width: 1200px) {

  .image-col{
    width: 100%;
    text-align: center;
  }
  .image {
    width: 90px;
    height: 90px;
    border: 5px solid white;
    margin-left: 50%;
  }


  .text-col {
    margin-top: -20px;
    margin-bottom: 10px;
    margin-left: 0px;
    
  }

  .text-col>p {
    font-size: 1.1em;
    font-weight: bold;
    margin-bottom: 5px;
    width: 100%;
    text-align: center;
  }

    .show{
      display: block;
    }

    .gone-mid{
      display: none;
    }

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
        this.$emit("changeSite", "MyProfile")
      }
    },


  }
</script>