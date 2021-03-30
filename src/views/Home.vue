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
</style>