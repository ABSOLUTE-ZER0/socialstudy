<template>
  <b-row class="comp">
    <b-button @click="displayModal=true;selectedCategory=null" class="create-button outline-button shadow-none"><i
        class="far fa-edit"></i> Create a post
    </b-button>
    <b-col @click="displayModal=true;selectedCategory='Assignment'" class="p-div">
      <p class="p"><i style="color: #2bd5a9" class="fas icon fa-clipboard-check"></i><br class="show"> Assignment</p>
    </b-col>
    <b-col @click="displayModal=true;selectedCategory='Material'" class="p-div">
      <p class="p"><i style="color: #7a75ff" class="fas fa-folder"></i><br class="show"> Material</p>
    </b-col>
    <b-col @click="displayModal=true;selectedCategory='Announcement'" class="p-div">
      <p class="p"><i style="color: rgb(255, 174, 0);" class="fas fa-bullhorn"></i><br class="show"> Announcement</p>

    </b-col>
    <b-col @click="displayModal=true;selectedCategory='Event'" class="p-div">
      <p class="p"><i style="color: black" class="far fa-newspaper"></i><br class="show"> Event</p>
    </b-col>

    <div v-if="displayModal">
      <div class="modal-mask createpostModal">
        <div class="modal-wrapper ">
          <div class="modal-dialog">
            <div class="modal-content">
              <b-icon @click="displayModal=false" class="exit-modal" icon="x"></b-icon>
              <div class="modal-title-div">
                <h1 class="modal-title shadow-none"><i class="far fa-edit"></i> Create a post</h1>
              </div>
              <b-form>
                <b-form-group>
                  <b-form-select class="modal-input" v-model="selectedCategory" :options="optionsCategory">
                  </b-form-select>
                </b-form-group>
                <b-form-group>
                  <b-form-select class="modal-input" v-model="selectedGroup" :options="optionsGroup"></b-form-select>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="modal-input" type="text" placeholder="Subject"></b-form-input>
                </b-form-group>
                <b-form-textarea class="modal-input" placeholder="What do you want to post about" no-resize rows="4">
                  <b-form-input type="text">
                  </b-form-input>
                </b-form-textarea>
                <b-button style="margin-left: 70%" class="button post-btn" @click="displayModal=false">Post</b-button>
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
    font-size: 1.2em;
    cursor: pointer;
  }

  .create-button {
    width: 100%;
    margin: 1em 2em;
    text-align: left;
    border-radius: 2em;
    font-size: 1.2em;
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
    margin: 40px 5% 20px;
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

  .post-btn {
    margin: 1em 1em 2em;
    width: 20%;
    background-color: #01C4C9;
    border: 0;
  }


  .exit-modal {
    cursor: pointer;
    color: red;
    font-size: 2.5em;
    position: absolute;
    top: 0.2em;
    right: 0.5em;
  }

  .show {
    display: none;
  }


  @media (max-width: 1650px) {
    .p {
      font-size: 1em;
    }

    .show {
      display: block;
    }
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
        displayModal: false,
        selectedGroup: null,
        selectedCategory: null,
        optionsCategory: [{
            value: null,
            text: "Select Category",
            disabled: true
          },
          {
            value: 'Assignment',
            text: 'Assignment'
          },
          {
            value: 'Material',
            text: 'Material'
          },
          {
            value: 'Announcement',
            text: 'Announcement'
          },
          {
            value: 'Event',
            text: 'Event'
          }
        ],
        optionsGroup: [{
            value: null,
            text: "Select Group",
            disabled: true
          },
          {
            value: 'Class',
            text: 'Class'
          },
          {
            value: 'Section',
            text: 'Section'
          }
        ]
      }
    }
  }
</script>