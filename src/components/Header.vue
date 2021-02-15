<template>
  <div class="main-div">
    <b-container fluid>
      <b-row>
        <b-col cols="3">
          <h1>socialstudy</h1>
          <b-input-group class="searchbar-div mb-2" size="sm">
            <b-input-group-prepend is-text>
              <b-icon icon="search"></b-icon>
            </b-input-group-prepend>
            <b-form-input class="searchbar" type="search" placeholder="Search"></b-form-input>
          </b-input-group>
        </b-col>
        <b-col class="options" cols="6">
          <div class="icon-div">
            <b-icon  class="icon" icon="clipboard" font-scale="3"></b-icon>
            <p class="icon-text">Notice Board</p>
          </div>
          <div class="icon-div">
            <b-icon class="icon" icon="book" font-scale="3"></b-icon>
            <p class="icon-text">Library</p>
          </div>
          <div class="icon-div">
            <b-icon class="icon" icon="building" font-scale="3"> </b-icon>
            <p class="icon-text">Institute</p>
          </div>
          <div class="icon-div">
            <b-icon class="icon" icon="person-plus" font-scale="3"> </b-icon>
            <p class="icon-text">Connections</p>
          </div>
        </b-col>
        <b-col style="margin-top: 1em" class="options" cols="3">

          <div style="margin-left: 10%" class="icon-div">
            <button class="icon1 fas fa-2x fa-bell"></button>
            <p class="icon-text">Message</p>
          </div>
          <div class="icon-div">
            <button class="icon1 fas fa-2x fa-comment-dots"></button>
            <p class="icon-text">Notification</p>
          </div>
          <div class="icon-div">
            <button class="icon1 fas fa-user fa-2x"></button>
            <p class="icon-text">My Profile</p>
          </div>


        </b-col>

      </b-row>
    </b-container>
  </div>
</template>

<script>
  export default {

  }
</script>

<style scoped>
  .main-div {
    background-color: rgb(255, 255, 255);
    padding-top: 2em;
    max-width: 100%;
  }



  h1 {
    color: rgb(0, 203, 218);
    font-size: 3em !important;
  }

  .options {
    display: inline-flex !important;
  }


  .input-group-prepend{
    border-top-left-radius: 5em  !important;
    border-bottom-left-radius: 5em !important;
  }

  .searchbar-div{
    width: 15em;
  }

  .searchbar{
    border-radius: 5em !important;
    border-top-left-radius: 0  !important;
    border-bottom-left-radius: 0 !important;
  }

  .icon {
    width: 100%;
  }

    .icon1 {
    width: 100%;
    border: none;
    background-color: white;
  }

  .icon-text {
    width: 100%;
    margin-top: 0.5em;
  }

  .icon-div{
    padding: 2em;
    text-align: center;
  }
</style>