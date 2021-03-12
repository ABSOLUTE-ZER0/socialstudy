<template>
  <div class="main-div">
    <b-container fluid>
      <b-row>


        <b-col lg="3" v-if="check()">
          <Create v-if="siteNameProp == 'Institute'" />
          <Details v-if="siteNameProp != 'Institute'" />
          <Tools v-on:changeSite="updateSite($event);changePage()" />
        </b-col>

        <b-col lg="9" sm="12">
          <NoticeBoard v-if="siteNameProp == 'NoticeBoard'" />
          <Library v-if="siteNameProp == 'Library'" />
          <Institute v-on:instituteView="instituteView($event);" v-if="siteNameProp == 'Institute'" />
          <Connections v-if="siteNameProp == 'Connections'" />
          <ToolView :pageName="view" v-if="siteNameProp == 'ToolView'" />
        </b-col>
        <b-col lg="12" v-if="!check()">
          <InstituteView v-if="siteNameProp == 'Institute'" />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>


<style scoped>

</style>



<script>
  import NoticeBoard from "./NoticeBoard"
  import Tools from "./Tools"
  import Library from "./Library"
  import InstituteView from "./InstituteView"
  import Institute from "./Institute"
  import Connections from "./Connections"
  import ToolView from "./ToolView"
  import Details from "./Details"
  import Create from "./CreateInstitute"

  export default {
    data() {
      return {
        siteName: "NoticeBoard",
        view: "",
        institute: "",
        list: ["InstituteView", "Institute"]
      }
    },
    components: {
      NoticeBoard,
      Tools,
      Library,
      Connections,
      ToolView,
      Details,
      InstituteView,
      Create,
      Institute
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
      instituteView(value) {
        this.institute = value
      },
      check() {
        if (this.institute == this.list[0] && this.siteNameProp == this.list[1]) {
          return false
        } else {
          this.institute = ""

          return true
        }
      }

    },
    props: {
      siteNameProp: String
    }
  }
</script>