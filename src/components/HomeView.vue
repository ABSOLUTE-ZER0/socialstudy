<template>
  <div class="main-div" v-if="page!='subjectDetails'">
    <b-container fluid>
      <b-row>
        <b-col lg="3" v-if="check()">
          <Create v-on:instituteViewAdmin="instituteViewAdmin($event);" v-if="siteNameProp == 'Institute'" />
          <Details v-on:changeSite="updatePage($event)" v-if="siteNameProp != 'Institute'" />
          <Tools v-on:changeSite="updateSite($event);changePage()" />
        </b-col>

        <b-col lg="9" sm="12" style="padding: 0">
          <NoticeBoard v-if="siteNameProp == 'NoticeBoard'" />
          <Library v-if="siteNameProp == 'Library'" />
          <Institute v-on:instituteView="instituteView($event);" :propView="propView"
            v-if="siteNameProp == 'Institute'" />
          <Connections v-if="siteNameProp == 'Connections'" />
          <ToolView :pageName="view" v-if="siteNameProp == 'ToolView'" />
        </b-col>
        <b-col lg="12" v-if="!check()">
          <InstituteView v-on:subjectDetailsPage="updatePage($event)" :isAdmin="instituteAdmin"
            v-if="siteNameProp == 'Institute'" />
        </b-col>
      </b-row>
      <div>
        <Friends v-if="siteNameProp == 'NoticeBoard'" />
      </div>
    </b-container>
    <div v-if="page=='subjectDetails'">
      <SubjectDetails />
    </div>
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
  import Friends from "./Friends"


  export default {
    data() {
      return {
        siteName: "NoticeBoard",
        view: "",
        institute: "",
        list: ["InstituteView", "Institute"],
        instituteAdmin: false,
        page: ""
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
      Institute,
      Friends
    },
    methods: {
      updateSite(newValue) {
        this.view = newValue;
        newValue = "ToolView";
        this.siteName = newValue;
      },
      changePage() {
        this.$emit("changeSite", [this.siteName])
      },
      updatePage(value) {
        this.$emit("changeSite", [value])
      },
      instituteView(value) {
        this.institute = value[0]
        this.instituteAdmin = value[1]
      },
      instituteViewAdmin(value) {
        this.institute = value[0]
        this.instituteAdmin = value[1]
        this.propView = "false"
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
      siteNameProp: String,
      propView: String
    }
  }
</script>