<template>
  <div class="main-div">
    <b-container fluid>
      <b-row>

        <b-col cols="3">
          <h1>socialstudy</h1>
          <b-input-group class="searchbar-div mb-2" size="sm">
            <b-input-group-prepend is-text>
              <b-icon icon="search"></b-icon>
            </b-input-group-prepend>
            <b-form-input class="searchbar" type="search" placeholder="Search"></b-form-input>
          </b-input-group>
        </b-col>

        <b-col class="options" cols="6">
          <b-navbar style="text-align:center" toggleable="lg">
            <b-navbar-nav>
              <b-nav-item @click="pageName='NoticeBoard';changePage()" class="nav-item">
                <b-icon class="icon" icon="clipboard" font-scale="3"></b-icon>Notice Board
              </b-nav-item>

              <b-nav-item @click="pageName='Library';changePage()" class="nav-item">
                <b-icon class="icon" icon="book" font-scale="3"></b-icon>Library
              </b-nav-item>

              <b-nav-item @click="pageName='Institute';changePage()" class="nav-item">
                <b-icon class="icon" icon="building" font-scale="3"> </b-icon>Institute
              </b-nav-item>

              <b-nav-item @click="pageName='Connections';changePage()" class="nav-item">
                <b-icon class="icon" icon="person-plus" font-scale="3"></b-icon>Connections
              </b-nav-item>
            </b-navbar-nav>
          </b-navbar>
        </b-col>

        <b-col style="margin-top: 1em" class="options" cols="3">
          <b-navbar right toggleable="lg">
            <b-navbar-toggle target="nav-collapse"></b-navbar-toggle>
            <b-collapse style="text-align: center;" id="nav-collapse" is-nav>
              <b-navbar-nav class="ml-auto">
                <b-nav-item @click="pageName='Message';changePage()" href="#"><button class="icon1 fas fa-2x fa-bell"></button>Message</b-nav-item>
                <b-nav-item @click="pageName='Notification';changePage()" href="#"><button class="icon1 fas fa-2x fa-comment-dots"></button>Notification</b-nav-item>
                <b-nav-item @click="pageName='MyProfile';changePage()" href="#"><button class="icon1 fas fa-user fa-2x"></button>My Profile</b-nav-item>
              </b-navbar-nav>
            </b-collapse>
          </b-navbar>
        </b-col>

      </b-row>
    </b-container>
  </div>
</template>



<style scoped>
  .main-div {
    background-color: rgb(255, 255, 255);
    padding-top: 2em;
    max-width: 100%;
    max-height: 10em;
  }



  h1 {
    color: rgb(0, 203, 218);
    font-size: 3em !important;
  }



  .input-group-prepend {
    border-top-left-radius: 5em !important;
    border-bottom-left-radius: 5em !important;
  }

  .searchbar-div {
    width: 15em;
  }

  .searchbar {
    border-radius: 5em !important;
    border-top-left-radius: 0 !important;
    border-bottom-left-radius: 0 !important;
  }

  .icon {
    width: 100%;
  }

  .icon1 {
    width: 100%;
    border: none;
    background-color: white;
  }

  .icon-text {
    width: 100%;
    margin-top: 0.5em;
  }

  .icon-div {
    padding: 2em;
    text-align: center;
  }
</style>



<script>
  export default {
    data() {
      return{
        pageName: "NoticeBoard"
      }
    },
    methods:{
      changePage: function(){
        this.$emit("changeSite", this.pageName)
      }
    }

  }
</script>