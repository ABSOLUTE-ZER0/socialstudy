<template>
  <div>
    <Header v-on:changeSite="updateSite($event)"  />
    <NoticeBoard v-if="siteName == 'NoticeBoard'"/>
    <Profile  v-if="siteName == 'MyProfile'" />
  </div>
</template>

<script>
import Header from "../components/Header";
import NoticeBoard from "../components/NoticeBoard";
import Profile from "../components/Profile"

export default {
  data() {
    return{
      siteName: 'NoticeBoard'
    }
  },
  components:{
    Header,
    NoticeBoard,
    Profile
  },
  methods:{
    updateSite(newValue){
      this.siteName=newValue;
    }
  }
}
</script>

<style>
body{
  background-color: rgb(236, 236, 236) !important;
}
</style>