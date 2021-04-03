<template>
  <b-navbar class="navbar-div" style="margin-top: 1em">
    <b-navbar-nav>
      <b-nav-item v-for="item in items" :key="item" @click="pageName=item.pageName;changePage()"
        v-bind:class="{'active-tool': pageName==active&&pageName==item.pageName}" class="navitem tools-nav">
        <i :style="item.color" :class="item.imgclass"></i> {{ item.name }}
      </b-nav-item>
    </b-navbar-nav>
  </b-navbar>
</template>

<style scoped>
  .navitem {
    text-align: center;
    flex: 1;
    font-weight: bold;
  }

  .tools-nav>.nav-link {
    color: black !important;
  }

  .tools-nav>.nav-link>i {
    font-size: 3em;
  }

  .navbar-div {
    width: 100%;
  }

  .navbar-nav {
    width: 100%;
  }

  .icon {
    width: 100%;
  }

  .active-tool>.nav-link>i {
    font-size: 4em;
  }

  @media (max-width: 768px) {
    .tools-nav {
      padding: 0;
    }

    .navbar {
      padding: 0;
    }
  }
</style>


<script>
  export default {
    data() {
      return {
        style: "",
        pageName: " ",
      }
    },
    props: {
      items: Array,
      active: String
    },
    methods: {
      changePage: function () {
        this.$emit("changeSite", this.pageName)
      }
    },
    isActive(name) {
      if (this.pageName == name) {
        return true
      } else {
        return false
      }
    }
  }
</script>