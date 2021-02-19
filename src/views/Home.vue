<template>
  <div style="background-color: rgb(236, 236, 236); min-height: 100vh">
    <Header v-on:changeSite="updateSite($event)" />
    <HomeView :siteNameProp="siteName" v-on:changeSite="updateSite($event);changePage()" v-if="options.find(check)==siteName" />
    <Profile v-if="siteName == 'MyProfile'" />
    <Institute v-if="siteName == 'Institute'"/>
  </div>
</template>

<script>
  import Header from "../components/Header";
  import HomeView from "../components/HomeView";
  import Profile from "../components/Profile";
  import Institute from "../components/Institute";



  export default {
    data() {
      return {
        siteName: 'NoticeBoard',
        options: ["NoticeBoard", "Library", "Connections", "ToolView"]

      }
    },
    components: {
      Header,
      HomeView,
      Profile,
      Institute
    },
    methods: {
      updateSite(newValue) {
        this.siteName = newValue;
      },
      check(name){
        if(this.siteName == name)
         return true
      }

    }
  }
</script>

<style>
</style>