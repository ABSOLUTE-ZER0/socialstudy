<template>
  <div>
    <Header v-on:changeSite="updateSite($event)" />
    <Options :siteNameProp="siteName" v-on:changeSite="updateSite($event);changePage()" v-if="options.find(check)==siteName" />
    <Profile v-if="siteName == 'MyProfile'" />
  </div>
</template>

<script>
  import Header from "../components/Header";
  import Options from "../components/Options";
  import Profile from "../components/Profile";



  export default {
    data() {
      return {
        siteName: 'NoticeBoard',
        options: ["NoticeBoard", "Library"]

      }
    },
    components: {
      Header,
      Options,
      Profile
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
  body {
    background-color: rgb(236, 236, 236) !important;
  }
</style>