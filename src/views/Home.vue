<template>
  <div style="background-color: #f3f7f7; min-height: 100vh;padding: 0 10%;overflow-x: hidden;">
    <Header v-on:changeSite="updateSite($event)" />
    <HomeView :propView="propView" :siteNameProp="siteName" v-on:changeSite="updateSite($event);changePage()"
      v-if="options.find(check)==siteName" />
    <Profile v-if="siteName == 'MyProfile'" />
    <SubjectDetails v-if="siteName == 'SubjectDetails'"/>
  </div>
</template>

<script>
  import Header from "../components/Header";
  import HomeView from "../components/HomeView";
  import Profile from "../components/Profile";
  import SubjectDetails from "../components/SubjectDetails"



  export default {
    data() {
      return {
        siteName: 'NoticeBoard',
        options: ["NoticeBoard", "Library", "Institute", "Connections", "ToolView"],
        propView: "true"
      }
    },
    components: {
      Header,
      HomeView,
      Profile,
      SubjectDetails,
    },
    methods: {
      updateSite(newValue) {
        console.log(newValue);
        this.siteName = newValue[0];
        if (this.siteName == 'Institute') {
          this.propView = newValue[1]
        }
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
    border: 0 !important;
    background: none !important;
  }


  .outline-button {
    color: #01C4C9 !important;
    border: 1px solid #01C4C9 !important;
    background-color: #ffffff !important;

  }

  .outline-button:hover,
  .outline-button:active,
  .outline-button:focus {
    color: #ffffff !important;
    background-color: #01C4C9 !important;
    box-shadow: none !important;
  }
</style>