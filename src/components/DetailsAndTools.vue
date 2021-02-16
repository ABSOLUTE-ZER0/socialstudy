<template>
  <div>
    <b-row style="padding: 1em" class="comp">
      <b-col style="text-align: center; margin-right: 2em" cols="12" md="auto">
        <b-row>
          <b-img style="margin-bottom: 1em" v-bind="mainProps" rounded="circle" alt="Circle image"></b-img>
        </b-row>
        <b-button variant="link" @click="pageName='MyProfile';changePage()">My Profile </b-button>
      </b-col>
      <b-col>
        <p>Name</p>
        <p>Institution</p>
        <p>Year and Branch</p>
        <p>Position</p>
      </b-col>
    </b-row>
    <b-row class="comp">
      <b-col>
        <b-row>
          <h4 style="margin: 2em; font-weight: bold; margin-bottom: 0;margin-top: 1em;">Tools</h4>
        </b-row>
        <b-row>
          <b-col>

            <b-navbar style="margin-top: 1em">
              <b-navbar-nav>
                <b-nav-item class="tool" @click="pageName='';changePage()">
                  <i class="fas fa-4x icon fa-video"></i>Start Live Class
                </b-nav-item>
                <b-nav-item class="tool" @click="pageName='';changePage()">
                  <i class="fas fa-4x icon fa-folder"></i>File Sharing
                </b-nav-item>
              </b-navbar-nav>
            </b-navbar>

            <b-navbar>
              <b-navbar-nav>
                <b-nav-item class="tool" @click="pageName='';changePage()">
                  <i class="fas fa-4x icon fa-clipboard-check"></i>Assignment
                </b-nav-item>
                <b-nav-item class="tool" @click="pageName='';changePage()">
                  <i class="fas fa-4x icon fa-users"></i>Manage Group
                </b-nav-item>
              </b-navbar-nav>
            </b-navbar>

            <b-navbar>
              <b-navbar-nav>
                <b-nav-item class="tool" @click="pageName='';changePage()">
                  <i class="fas fa-4x icon fa-clipboard-list"></i>Attendance
                </b-nav-item>
                <b-nav-item class="tool" @click="pageName='';changePage()">
                  <i class="fas fa-4x icon fa-file-alt"></i>Report Card
                </b-nav-item>
              </b-navbar-nav>
            </b-navbar>

          </b-col>
        </b-row>
      </b-col>
    </b-row>

  </div>

</template>


<style scoped>
  .tools-img {
    min-width: 8em;
    margin: 1em 3em !important;
    border: 0;
    text-align: center;
  }

  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  .tool {
    text-align: center;
    margin: 1em 2em;
  }

  .icon {
    width: 100%;
  }

</style>

<script>
  export default {
    data() {
      return {
        pageName: "MyProfile",
        mainProps: {
          blank: true,
          blankColor: '#777',
          width: 130,
          height: 130,
          class: 'profile-img'
        }
      }
    },
    methods: {
      changePage: function () {
        this.$emit("changeSite", this.pageName)
      }
    }

  }
</script>