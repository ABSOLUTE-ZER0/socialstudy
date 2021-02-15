<template>
  <div class="main-div">
    <b-container fluid>
      <b-row>
        <b-col cols="3">
          <b-row style="padding-top: 1em" class="comp">
            <b-col cols="5">
              <b-img v-bind="mainProps" rounded="circle" alt="Circle image"></b-img>
              <a style="margin-left: 20%" href="/">My Profile </a>
            </b-col>
            <b-col>
              <p>Name</p>
              <p>Institution</p>
              <p>Year and Branch</p>
              <p>Position</p>
            </b-col>
          </b-row>
          <b-row class="comp">
            <b-row>
              <h4 style="margin: 2em; font-weight: bold; margin-bottom: 0;margin-top: 1em;">Tools</h4>
            </b-row>
            <b-row>
              <b-col>
                <b-card-group deck>
                  <b-card class="tools-img" img-src="https://placekitten.com/1000/300" img-alt="Card image" img-top>
                    <b-card-text>
                      Start Live Class
                    </b-card-text>
                  </b-card>

                  <b-card class="tools-img" img-src="https://placekitten.com/1000/300" img-alt="Card image" img-top>
                    <b-card-text>
                      File Sharing
                    </b-card-text>
                  </b-card>
                  <b-card class="tools-img" img-src="https://placekitten.com/1000/300" img-alt="Card image" img-top>
                    <b-card-text>
                      Assignment
                    </b-card-text>
                  </b-card>
                  <b-card class="tools-img" img-src="https://placekitten.com/1000/300" img-alt="Card image" img-top>
                    <b-card-text>
                      Manage Group
                    </b-card-text>
                  </b-card>
                  <b-card class="tools-img" img-src="https://placekitten.com/1000/300" img-alt="Card image" img-top>
                    <b-card-text>
                      Attendance
                    </b-card-text>
                  </b-card>
                  <b-card class="tools-img" img-src="https://placekitten.com/1000/300" img-alt="Card image" img-top>
                    <b-card-text>
                      Report Card
                    </b-card-text>
                  </b-card>
                </b-card-group>
              </b-col>
            </b-row>
          </b-row>
        </b-col>
        <b-col class="" cols="6">
          <div class="icon-div">

          </div>
          <div class="icon-div">

          </div>
        </b-col>
        <b-col style="margin-top: 10em" class="comp" cols="2">
          <b-row style="padding: 1em">
            <h4 style="font-weight: bold">Online Friends</h4>
          </b-row>
          <b-row class="friends-row">
            <b-col cols="3">
              <b-img class="friends-img" src="https://placekitten.com/1000/300" rounded="circle" alt="Circle image"></b-img>
            </b-col>
            <b-col cols="9">
              <p class="friends-name">Friends Name</p>
            </b-col>
          </b-row>


        </b-col>

      </b-row>
    </b-container>
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

  .card-body {
    padding: 0;
  }

  .card-img-top {
    min-height: 7.5em !important;
    border-radius: 1em;

  }

  .friends-name{
    font-size: 1.4em;
    margin-top: 0.8em;
  }

  .friends-img{
    width: 4em !important;
    height: 4em;
  }


</style>



<script>
  export default {
    data() {
      return {
        mainProps: {
          blank: true,
          blankColor: '#777',
          width: 130,
          height: 130,
          class: 'm1'
        }
      }
    }
  }
</script>