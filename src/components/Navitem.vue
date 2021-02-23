<template>
  <b-navbar class="navbar-div" style="margin-top: 1em">
    <b-navbar-nav>
      <b-nav-item v-for="item in items" :key="item" class="navitem tools-nav" @click="pageName=item.pageName;changePage()">
        <i :class="item.imgclass"></i> {{ item.name }}
      </b-nav-item>
    </b-navbar-nav>
  </b-navbar>
</template>

<style scoped>
  .navitem {
    text-align: center;
    padding: 1em 2em;

  }

    .icon {
    width: 100%;
  }

  @media (max-width: 768px){
    .tools-nav{
  padding: 0;
}
.navbar{
  padding: 0;
}
  }
</style>


<script>
export default {
  data(){
    return{
        pageName: "MyProfile",

    }
  },
  props: {
    items: Array
  },
      methods: {
      changePage: function () {
        this.$emit("changeSite", this.pageName)
      }
    }
}
</script>