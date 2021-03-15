<template>
  <div>
    <b-button @click="displayModal=true" class="create-btn">+ Create New Institute</b-button>
    <div class="comp">
      <h4 class="title1">Institutes created</h4>
      <b-row v-for="sub in institutesCreated" :key="sub" class="cards">
        <b-col>
          <b-card class="card9" img-left :img-src="sub.src">
            <b-card-body class="body">
              <b-card-title class="title"> {{sub.name}} </b-card-title>
              <b-card-sub-title class="sub mb-2"> {{sub.sub1}}</b-card-sub-title>
            </b-card-body>
          </b-card>
        </b-col>
      </b-row>
    </div>


    <div v-if="displayModal">
      <div class="modal-mask createpostModal">
        <div class="modal-wrapper ">
          <div class="modal-dialog">
            <div class="modal-content">
              <b-icon @click="displayModal=false" class="exit-modal" icon="x"></b-icon>

              <h1 class="modal-title shadow-none"><i class="far fa-edit"></i> Create...</h1>
              <b-form>
                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="College/School/Coaching/Other">
                  </b-form-input>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="Institute Name"></b-form-input>
                </b-form-group>
                <div class="form-row">
                    <b-form-input class="input-samerow" type="text" placeholder="Country"></b-form-input>
                    <b-form-input class="input-samerow" type="text" placeholder="State"></b-form-input>
                </div>

                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="City"></b-form-input>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="Course Name (e.g B.tech/ BBA)"></b-form-input>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="Specialization/Department (IT/CS/Civil)">
                  </b-form-input>
                </b-form-group>

                <b-button style="margin-left: 70%" class="post-btn" @click="displayModal=false">Post</b-button>
              </b-form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>

</template>

<style scoped>
  .card-img-left {
    border: 0;
    width: 3em;
    height: 3em;
    margin-top: 0.5em;
    border-radius: 50%;
  }


  .title1 {
    padding: 0.5em 1em 0;
  }


  .cards {
    margin: 1em 0;
    margin-left: 0.5em;
  }

  .create-btn {
    background-color: #01C4C9;
    border: 0;
    width: 90%;
    border-radius: 2em;
    margin: 1em 1em 0;
    border: 1px solid #01c4c9 !important;
    font-size: 1.5em;
  }

  .create-btn:hover,
  .create-btn:focus,
  .create-btn:active {
    background-color: #ffffff !important;
    color: #01C4C9 !important;
    border: 1px solid #01c4c9 !important;

  }


  .card-body {
    padding: 0;
  }

  .body {
    padding: 1em;
    padding-bottom: 0;
  }

  .card {
    border: 0;
    width: 100%;
  }

  .title {
    font-size: 0.9em;
  }

  .sub {
    color: black !important;
    font-size: 0.8em;
  }



  .createpostModal {
    position: fixed;
    z-index: 200;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .5);
    display: table;
    transition: opacity .3s ease;
  }

  .modal-title {
    color: #01C4C9;
    width: fit-content;
    margin: 5% 5% 0;
    border-bottom: 1px solid #01C4C9;
  }

  .modal-dialog {
    pointer-events: all !important;
    max-width: none !important;
    min-width: 100% !important;
    padding: 0 10%;
    margin: 0;
  }

  .modal-wrapper {
    display: table-cell;
    vertical-align: middle;

  }

  .modal-content {
    width: 80%;
    margin-left: 10%;
  }

  .form-row{
    width: 100%;
    display: flex;
    flex-flow: row wrap;
  }

  .input-samerow{
    background-color: #EAFDFB;
    border: 0;
    margin: 1em 5%;
    border-radius: 0.5em;
    font-size: 1.5em;
    width: 40%;
  }

  .input {
    background-color: #EAFDFB;
    border: 0;
    margin: 1em 5% 0;
    border-radius: 0.5em;
    font-size: 1.5em;
    width: 90%;
  }

  .post-btn {
    margin: 1em;
    width: 20%;
    background-color: #01C4C9;
    border: 0;
  }


  .exit-modal {
    color: red;
    font-size: 2.5em;
    position: absolute;
    top: 0.2em;
    right: 0.5em;
  }
</style>

<script>
  export default {
    data() {
      return {
        view: false,
        displayModal: false,
        institutesCreated: [{
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Data Structures & Algorithm",
            sub1: "3rd Semester"
          },
          {
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Data Structures & Algorithm",
            sub1: "3rd Semester"
          }
        ],
      }
    },


  }
</script>