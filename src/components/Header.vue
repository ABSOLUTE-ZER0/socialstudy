<template>
  <div class="shadow main-div">
    <b-container fluid>
      <b-row>
        <b-col cols="10" md="3">
          <h1>socialstudy</h1>
          <b-input-group class="searchbar-div mb-2" size="sm">
            <b-input-group-prepend is-text>
              <b-icon icon="search"></b-icon>
            </b-input-group-prepend>
            <b-form-input class="searchbar" type="search" placeholder="Search"></b-form-input>
          </b-input-group>
        </b-col>
        <b-col style="margin-top: 1em" class="options" cols="10" md="6">
          <b-navbar style="text-align:center; padding: 0">
            <b-navbar-nav style="width:100%">
              <b-nav-item @click="pageName='NoticeBoard';changePage()" class="navitem">
                <b-icon class="icon" icon="clipboard" font-scale="3"></b-icon>Notice Board
              </b-nav-item>
              <b-nav-item @click="pageName='Library';changePage()" class="navitem">
                <b-icon class="icon" icon="book" font-scale="3"></b-icon>Library
              </b-nav-item>
              <b-nav-item @click="pageName='Institute';changePage()" class="navitem">
                <b-icon class="icon" icon="building" font-scale="3"></b-icon>Institute
              </b-nav-item>
              <b-nav-item @click="pageName='Connections';changePage()" class="navitem">
                <b-icon class="icon" icon="person-plus" font-scale="3"></b-icon>Connections
              </b-nav-item>
            </b-navbar-nav>
          </b-navbar>
        </b-col>
        <b-col style="margin-top: 1em" class="options drop-down-div" cols="2" md="3">
          <b-navbar style="padding: 0" right toggleable="lg">
            <b-navbar-toggle class="drop-down-button" target="nav-collapse"></b-navbar-toggle>
            <b-collapse style="text-align: center;z-index: 4" id="nav-collapse" is-nav>
              <b-navbar-nav class="ml-auto drop-down">
                <b-nav-item @click="pageName='Message';changePage()" class="navitem2" href="#"><button
                    class="icon1 fas fa-2x fa-comment-dots"></button>Message</b-nav-item>
                <b-nav-item @click="pageName='Notification';changePage()" class="navitem2" href="#"><button
                    class="icon1 fas fa-2x fa-bell"></button>Notification</b-nav-item>
                <b-nav-item @click="profileClick()" class="navitem2 profile-dropdown" href="#">
                  <button class="icon1 fas fa-user fa-2x"></button>My Profile</b-nav-item>
                  <div class="profile-dropdown-div shadow" v-if="profileDropdown">
                    <b-nav-item @click="pageName='MyProfile';changePage()">My Profile</b-nav-item>
                    <b-nav-item>Settings</b-nav-item>
                    <b-button variant="danger" class="logout" href="/">LOGOUT</b-button>
                  </div>
                <b-nav-item class="d-md-none">
                  <b-icon icon="search"></b-icon>Search
                </b-nav-item>

                
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
    padding: 2em 10% 0;
    width: 500%;
    max-height: 10em;
    padding: 0 200%;
    margin-left: -200%;
  }

  .navitem2{
    max-height: 10px;
  }

  .profile-dropdown:after {
    content: " ";
    position: relative;
    right: -40px;
    top: -30px;
    border: solid black;
    border-width: 0 3px 3px 0;
    display: inline-block;
    padding: 3px;
    transform: rotate(45deg);
  }

  .profile-dropdown-div{
    position: absolute;
    top: 40px;
    right: 0;
    width: fit-content;
    overflow: hidden;
    background-color: white;
  }

  h1 {
    color: rgb(0, 203, 218);
    font-size: 3em !important;
  }

  .navitem {
    flex: auto;

  }

  .input-group-prepend {
    border-top-left-radius: 5em !important;
    border-bottom-left-radius: 5em !important;
  }

  .searchbar-div {
    width: 15em;
  }

  .drop-down {
    background-color: white;
  }

  .searchbar {
    border-radius: 5em !important;
    border-top-left-radius: 0 !important;
    border-bottom-left-radius: 0 !important;
  }

  .icon {
    width: 100% !important;
    font-size: 2.5em !important;
  }

  .icon1 {
    width: 100%;
    border: none;
    background-color: white;
  }

  .logout {
    height: fit-content;
  }



  @media (max-width: 992px) and (min-width: 768px) {
    .main-div {
      text-align: center;
    }
  }


  @media (max-width: 768px) {
    h1 {
      font-size: 2em !important;
      margin-bottom: 0 !important;
    }

    .icon {
      font-size: 2em !important;
      width: 100% !important;
    }

    .icon1 {
      font-size: 2em;
    }

    .navitem,
    .navitem2 {
      font-size: 1em;
      margin: 0 0 !important;
      margin-bottom: 1em !important;
    }

    .searchbar-div {
      display: none;
    }

    .drop-down-div {
      margin: 0;
      margin-left: -3em;
    }

    .logout {
      position: relative;
    }


    .options {
      z-index: 3;
      margin-top: 0 !important;
    }

    .drop-down-button {
      margin-top: 3em;
      font-size: 0.5em;
    }
  }
</style>
<script>
  export default {
    data() {
      return {
        pageName: "NoticeBoard",
        profileDropdown: false
      }
    }

    ,
    methods: {
      changePage: function () {
        this.$emit("changeSite", this.pageName)
      },
      profileClick(){
        this.profileDropdown = !this.profileDropdown;

      }
    }

  }
</script>