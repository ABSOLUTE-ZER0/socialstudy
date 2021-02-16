<template>
  <div class="main-div">
    <b-container fluid>
      <b-row>
        <b-col cols="3">
          <Tools v-on:changeSite="updateSite($event);changePage()" />
        </b-col>

        <b-col cols="9">
          <NoticeBoard v-if="siteNameProp == 'NoticeBoard'"/>
          <Library v-if="siteNameProp == 'Library'"/>
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

  export default {
    data() {
      return {
        siteName: "NoticeBoard",
      }
    },
    components: {
      NoticeBoard,
      Tools,
      Library
    },
    methods: {
      updateSite(newValue) {
        this.siteName = newValue;
      },
      changePage: function () {
        this.$emit("changeSite", this.siteName)
      }
    },
    props:{
      siteNameProp: String
    }
  }
</script>