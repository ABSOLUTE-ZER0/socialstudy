<template>
  <div class="main-div">
    <b-container fluid>
      <b-row>
        <b-col cols="12" lg="3" sm="12">
          <Tools v-on:changeSite="updateSite($event);changePage()" />
        </b-col>

        <b-col lg="9" sm="12">
          <NoticeBoard v-if="siteNameProp == 'NoticeBoard'"/>
          <Library v-if="siteNameProp == 'Library'"/>
          <Connections v-if="siteNameProp == 'Connections'"/>
          <ToolView :pageName="view" v-if="siteNameProp == 'ToolView'"/>
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>


<style scoped>

</style>



<script>
  import NoticeBoard from "./NoticeBoard"
  import Tools from "./DetailsAndTools"
  import Library from "./Library"
  import Connections from "./Connections"
  import ToolView from "./ToolView"


  export default {
    data() {
      return {
        siteName: "NoticeBoard",
        view: ""
      }
    },
    components: {
      NoticeBoard,
      Tools,
      Library,
      Connections,
      ToolView
    },
    methods: {
      updateSite(newValue) {
        this.view = newValue;
        newValue = "ToolView";
        this.siteName = newValue;

      },
      changePage() {
        this.$emit("changeSite", this.siteName)
      },

    },
    props:{
      siteNameProp: String
    }
  }
</script>