<template>
  <div>
    <b-button @click="displayModal=true" class="create-btn">+ Create New Institute</b-button>
    <div class="comp">
      <h4 class="title1">Institutes created</h4>
      <b-row v-for="sub in institutesCreated" :key="sub.id" class="cards">
        <b-col>
          <b-card @mouseover="hover=true,hoverId=sub.id" @mouseleave="hoverId=0" class="card9" img-left
            :img-src="sub.src">
            <b-card-body class="body">
              <b-card-title class="title"> {{sub.name}} </b-card-title>
              <b-card-sub-title class="sub mb-2"> {{sub.sub1}}</b-card-sub-title>
            </b-card-body>
            <div v-bind:class="{'hover':hover}" v-if="hoverId==sub.id">
              <div class="hoverDisplay" v-for="item in sub.branch" :key="item.id">
                <b-button @click="changePageAdmin()" class='hover-button'>{{ item.name }}</b-button>
              </div>
            </div>
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
              <div class="modal-title-div">
                <h1 class="modal-title shadow-none"><i class="far fa-edit"></i> Create new institute</h1>
              </div>
              <b-form>
                <b-form-group>
                  <b-form-input class="modal-input" type="text" placeholder="College/School/Coaching/Other">
                  </b-form-input>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="modal-input" type="text" placeholder="Institute Name"></b-form-input>
                </b-form-group>
                <div class="form-row">
                  <b-form-input class="input-samerow" type="text" placeholder="Country"></b-form-input>
                  <b-form-input class="input-samerow" type="text" placeholder="State"></b-form-input>
                </div>

                <b-form-group>
                  <b-form-input class="modal-input" type="text" placeholder="City"></b-form-input>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="modal-input" type="text" placeholder="Course Name (e.g B.tech/ BBA)">
                  </b-form-input>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="modal-input" type="text" placeholder="Specialization/Department (IT/CS/Civil)">
                  </b-form-input>
                </b-form-group>

                <b-button style="margin-left: 70%" class="button post-btn" @click="displayModal=false">Post</b-button>
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
    width: 40px;
    height: 40px;
    margin-top: 0.5em;
    border-radius: 50%;
  }


  .title1 {
    text-transform: uppercase;
    font-weight: bold;
    border-bottom: 1.5px solid rgba(0, 0, 0, 0.274);
    padding: 20px 1em 10px;
    font-size: 1.5em;
  }


  .cards {
    padding: 0.8em 0;
  }

  .card9:hover,
  .card9:focus,
  .card9:active {
    background-color: #dadada !important;
  }



  .create-btn {
    background-color: #01C4C9;
    width: 100%;
    border-radius: 2em;
    margin: 1em 0 0;
    border: 1px solid #01c4c9 !important;
    font-size: 1.5em;
  }

  .create-btn:hover,
  .create-btn:focus,
  .create-btn:active {
    background-color: #f3f7f7 !important;
    color: #01C4C9 !important;
    border: 1px solid #01c4c9 !important;
  }


  .hover-button:hover,
  .hover-button:focus,
  .hover-button:active {
    background-color: #a8a8a8 !important;
    color: #000000 !important;
    border: 0 !important;
  }

  .hover-button {
    width: 100%;
    background-color: transparent;
    border: 0;
    color: black;
    text-align: left;
    border-radius: 0;
    animation: scaleZ 300ms ease-in-out forwards;
    transform-origin: top center;
  }


  @keyframes scaleZ {
    0% {
      opacity: 0;
      transform: scale(0);
    }

    80% {
      transform: scale(1.07);
    }

    100% {
      opacity: 1;
      transform: scale(1);
    }
  }


  .card-body {
    padding: 0;
  }

  .body {
    padding: 0.8em 1em 0;
  }

  .hoverDisplay {
    width: 100%;

  }


  .card9 {
    padding-left: 1em;
  }

  .card {
    border: 0;
    width: 100%;
  }

  .title {
    font-size: 1em;
    font-weight: bold;
    margin-bottom: 8px;
  }

  .sub {
    color: black !important;
    font-size: 0.9em;
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

  .modal-title-div {
    width: 100%;
    border-bottom: 1.5px solid #a8a8a86c;
  }

  .modal-title {
    color: #01C4C9;
    margin: 20px 5% 20px;
    font-size: 2em;
    text-shadow: 2px 1px 1px #01c2c980;
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
    width: 60%;
    margin-left: 20%;
    border-radius: 1em;
  }


  .modal-input {
    background-color: #EAFDFB;
    border: 0;
    margin: 1em 5% 0;
    border-radius: 0.5em;
    font-size: 1.5em;
    width: 90%;
  }

  .form-row {
    width: 100%;
    display: flex;
    flex-flow: row wrap;
    margin: 0;
  }

  .input-samerow {
    background-color: #EAFDFB;
    border: 0;
    margin: 1em 5% 0;
    border-radius: 0.5em;
    font-size: 1.5em;
    width: 40%;
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
        hover: false,
        view: false,
        hoverId: 0,
        displayModal: false,
        institutesCreated: [{
            id: 1,
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Institute 1",
            sub1: "3rd Semester",
            branch: [
              {id: 1, name: "branch1"},
              {id: 2, name: "branch2"},
              {id: 3, name: "branch3"},
              {id: 4, name: "branch4"}
            ]
          },
          {
            id: 2,
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Institute 2",
            sub1: "3rd Semester",
            branch: [
              {id: 1, name: "branch1"},
              {id: 2, name: "branch2"}
            ]
          },
          {
            id: 3,
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Institute 3",
            sub1: "3rd Semester",
            branch: [
              {id: 1, name: "branch1"},
              {id: 2, name: "branch2"},
              {id: 3, name: "branch3"}
            ]
          }
        ],
      }
    },
    methods: {
      changePageAdmin() {
        this.$emit("instituteViewAdmin", ["InstituteView", true]);
        this.view = false;
      },
      showHover(id) {
        return id
      }
    },
    computed: {
      hoverDisplay() {
        for (var i in this.institutesCreated) {
          if (i.id == this.hoverId) {
            return i
          }
        }
        return null
      }
    }

  }
</script>