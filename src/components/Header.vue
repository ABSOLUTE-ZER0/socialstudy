<template>
  <div class="shadow main-div">
    <b-container fluid>
      <b-row>
        <b-col cols="10" md="3">
          <h1>socialstudy</h1>
          <b-input-group class="mb-2" size="sm">
            <div class="search-div">
              <b-icon icon="search"></b-icon>
              <input class="search-bar" type="text" placeholder="Search">
            </div>
          </b-input-group>
        </b-col>
        <b-col style="margin-top: 1em" class="options" cols="10" md="6">
          <b-navbar style="text-align:center; padding: 0">
            <b-navbar-nav style="width:100%">
              <b-nav-item @click="pageName='NoticeBoard';changePage()" v-bind:class="{'active-tab':isActive('NoticeBoard')}" class="navitem">
                <b-icon class="icon" icon="clipboard" font-scale="3"></b-icon>Notice
                Board
              </b-nav-item>
              <b-nav-item @click="pageName='Library';changePage()" v-bind:class="{'active-tab':isActive('Library')}" class="navitem">
                <b-icon class="icon" icon="book" font-scale="3"></b-icon>Library
              </b-nav-item>
              <b-nav-item @click="pageName='Institute';changePage()" v-bind:class="{'active-tab':isActive('Institute')}" class="navitem">
                <b-icon class="icon" icon="building" font-scale="3"></b-icon>Institute
              </b-nav-item>
              <b-nav-item @click="pageName='Connections';changePage()" v-bind:class="{'active-tab':isActive('Connections')}" class="navitem">
                <b-icon class="icon" icon="person-plus" font-scale="3"></b-icon>
                Connections
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
                  <button class="icon1 fas fa-user fa-2x"></button>Profile <b-icon class="dropdown-arrow" icon="triangle-fill"></b-icon></b-nav-item>
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

  .dropdown-arrow{
    font-size: 0.7em !important;
    transform: rotate(180deg);
    position: relative;
    top: -2px;
  }

  input:focus {
    outline: 0 !important;
  }

   .search-bar {
    border: 0;
    margin-left: 0.5em;
    width: calc(100% - 1.5em);
    background-color: transparent;
  }
  .search-div {
    width: 100%;
    margin: 0 1em;
    padding: 3px 1em;
    font-size: 1.2em;
    border-radius: 0.5em;
    border: 0;
    background-color: #f3f7f7;
    margin-left: 0;
  }

  .navitem2 {
    max-height: 10px;
    font-size: 0.9em;
    margin-top: 0.5em;
  }

  .profile-dropdown-div {
    position: absolute;
    top: 43px;
    left: 75%;
    width: 8em !important;
    width: fit-content;
    overflow: hidden;
    background-color: white;
    border-radius: 0.25em;
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


  .drop-down {
    background-color: white;
  }



  .icon {
    width: 100% !important;
    font-size: 2.5em !important;
    font-weight: bolder;
  }

  .icon1 {
    width: 100%;
    border: none;
    background-color: white;
  }

  .logout {
    height: fit-content;
    font-size: 1em;
    width: 100%;
  }

  .active-tab{
    border-bottom: 2px solid grey;
  }

  .active-tab>.nav-link{
    color: black !important;
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
        if(this.pageName == 'Institute'){
        this.$emit("changeSite", [this.pageName,"true"])
        }
        else{
        this.$emit("changeSite", [this.pageName])

        }
        this.profileDropdown = false
      },
      profileClick() {
        this.profileDropdown = !this.profileDropdown;
      },
      isActive(name){
        if(this.pageName == name){
          return true
        }
        else{
          return false
        }
      }
    }

  }
</script>