<template>
  <div style="background-color: rgb(236, 236, 236); min-height: 100vh;padding: 0 10%;overflow-x: hidden;">
    <Header v-on:changeSite="updateSite($event)" />
    <HomeView :siteNameProp="siteName" v-on:changeSite="updateSite($event);changePage()"
      v-if="options.find(check)==siteName" />
    <Profile v-if="siteName == 'MyProfile'" />
  </div>
</template>

<script>
  import Header from "../components/Header";
  import HomeView from "../components/HomeView";
  import Profile from "../components/Profile";



  export default {
    data() {
      return {
        siteName: 'NoticeBoard',
        options: ["NoticeBoard", "Library", "Institute", "Connections", "ToolView"]

      }
    },
    components: {
      Header,
      HomeView,
      Profile,
    },
    methods: {
      updateSite(newValue) {
        this.siteName = newValue;
      },
      check(name) {
        if (this.siteName == name)
          return true
      }

    }
  }
</script>

<style>
  .button {
    background-color: #01C4C9 !important;
    color: white !important;
    border: 1px solid #01C4C9 !important;
  }

  .button:hover,
  .button:active,
  .button:focus {
    color: #01C4C9 !important;
    background-color: #ffffff !important;
    box-shadow: none !important;
  }

  .no-outline-button {
    color: rgb(117, 117, 117) !important;
    background: none !important;
  }

  .no-outline-button:hover,
  .no-outline-button:active,
  .no-outline-button:focus {
    color: #01C4C9;
    background: none !important;
    box-shadow: none !important;
  }

  .outline-button {
    color: #01C4C9;
    border: 1px solid #01C4C9;
  }

  .outline-button:hover,
  .outline-button:active,
  .outline-button:focus {
    color: #ffffff !important;
    background-color: #01C4C9 !important;
    box-shadow: none !important;
  }

</style>