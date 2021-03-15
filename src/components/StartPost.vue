<template>
  <b-row class="comp">
    <b-button @click="displayModal=true" class="create-button shadow-none"><i class="far fa-edit"></i> Create...
    </b-button>
    <b-col class="p-div">
      <p class="p"><i class="fas fa-image"></i> Assignment</p>
    </b-col>
    <b-col class="p-div">
      <p class="p"><i class="fab fa-youtube"></i> Material</p>
    </b-col>
    <b-col class="p-div">
      <p class="p"><i class="fab fa-wpforms"></i> Announcement</p>

    </b-col>
    <b-col class="p-div">
      <p class="p"><i class="far fa-newspaper"></i> Event</p>
    </b-col>

    <div v-if="displayModal">
      <div class="modal-mask createpostModal">
        <div class="modal-wrapper ">
          <div class="modal-dialog">
            <div class="modal-content">
              <b-icon @click="displayModal=false" class="exit-modal" icon="x"></b-icon>

              <h1 class="title shadow-none"><i class="far fa-edit"></i> Create...</h1>
              <b-form>
                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="Select Category (Assign/Event/Ann/Mater)">
                  </b-form-input>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="Select Group (Class/Section)"></b-form-input>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="Select Subject"></b-form-input>
                </b-form-group>
                <b-form-textarea class="input" placeholder="Add Text...……." no-resize rows="4">
                  <b-form-input type="text">
                  </b-form-input>
                </b-form-textarea>
                <b-button style="margin-left: 70%" class="post-btn" @click="displayModal=false">Post</b-button>
              </b-form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </b-row>
</template>

<style scoped>
  .p-div {
    text-align: center;
    font-size: 1.3em;
    cursor: pointer;
  }

  .create-button {
    width: 100%;
    margin: 1em 2em;
    background-color: white;
    color: #01C4C9;
    text-align: left;
    border-radius: 2em;
    border: 1px solid rgb(218, 218, 218);
  }

  .create-button:hover,
  .create-button:focus,
  .create-button:active,
  .post-btn:hover,
  .post-btn:focus,
  .post-btn:active {
    background-color: #01C4C9 !important;
    color: white !important;
    border: 1px solid #01c4c9 !important;
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

  .title {
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


  @media (max-width: 768px) {
    .startpost-div {
      margin: 1em 2em !important;
    }

    .fa-edit {
      font-size: 0.7em;
    }

    .p {
      margin: 0 0 1em;
    }

    .p-div {
      padding: 0;
    }
  }
</style>

<script>
  export default {
    data() {
      return {
        displayModal: false
      }
    }
  }
</script>