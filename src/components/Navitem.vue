<template>
  <b-navbar class="navbar-div" style="margin-top: 1em">
    <b-navbar-nav>
      <b-nav-item v-for="item in items" :key="item" class="navitem tools-nav" @click="pageName=item.pageName;changePage()">
        <i :style="item.color" :class="item.imgclass"></i> {{ item.name }}
      </b-nav-item>
    </b-navbar-nav>
  </b-navbar>
</template>

<style scoped>
  .navitem {
    text-align: center;
    flex: 1;
  }

  .navbar-div{
      width: 100%;

  }

  .navbar-nav{
      width: 100%;

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
      style: "",
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