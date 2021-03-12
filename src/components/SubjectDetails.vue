<template>
  <div style="background-color: rgb(236, 236, 236); min-height: 100vh">
    <Header v-on:changeSite="updateSite($event)" />
    <b-container fluid>

      <b-row>
        <h1 class="sub-title">{{item.title}}</h1>
        <b-button class="upload-btn">Upload</b-button>
      </b-row>


      <b-row>
        <b-col lg="9">
          <b-navbar-nav class="nav-bar">
            <b-nav-item class="nav-item">Recorded lecture</b-nav-item>
            <b-nav-item class="nav-item">Live class recording</b-nav-item>
            <b-nav-item class="nav-item">Notes</b-nav-item>
            <b-nav-item class="nav-item">Assignment</b-nav-item>
            <b-nav-item class="nav-item">Question/Solution</b-nav-item>
          </b-navbar-nav>


          <div v-for="items in item2" :key="items" lg="9">
            <CardImg :src="items.src" class="comp card" :name="items.name" :sub1="items.year" />
          </div>
        </b-col>
        <b-col lg="3">
          <div class="comp filter">
            <h4>Filters</h4>
            <b-form-group class="filters" label="Chapter">
              <b-form-checkbox v-for="option in options" :key="option.value" :value="option.value">
                {{ option.text }}
              </b-form-checkbox>
            </b-form-group>
          </div>
        </b-col>
      </b-row>


    </b-container>
  </div>
</template>




<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  .comp.card {
    padding: 0.5em 2em 1em;
  }

  .filter{
    padding: 1em;
  }




  .sub-title {
    margin: 1em;
    margin-bottom: 0.5em;
    font-size: 3em;
  }

  .upload-btn {
    width: 10%;
    height: fit-content;
    margin: 3em 1em 0;
    margin-left: auto;
    background-color: #01C4C9;
    border: 1px solid #01C4C9;
    border-radius: 1em;
  }

  .upload-btn:hover,
  .upload-btn:focus,
  .upload-btn:active {
    background-color: #00a1a7 !important;
    border: 1px solid #00a1a7 !important;
    box-shadow: none !important;
  }

  .nav-bar {
    display: flex;
    flex-direction: row;
    width: 100%;
    margin-left: 2em;
  }

  .nav-item {
    flex: 1;
    font-size: 1.2em;
  }

  .nav-item a {
    color: black;
  }
</style>

<style>
  .filters>div>div>label{
    line-height: 1.8em;
    margin-top: 0.2em;
  }
</style>







<script>
  import Header from "../components/Header";
  import CardImg from "./Card-Img"




  export default {

    data() {
      return {
        options: [
          { text: 'All', value: 'all' },
          { text: 'Algebra', value: 'algebra' },
          { text: 'Set Theory', value: 'sets' },
          { text: 'Trigonometry', value: 'trigonometry' }
        ],
        item: {
          "title": "Subject Name"
        },
        item2: [{
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Data Structures & Algorithm",
          year: "3rd Semester"
        }, {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Data Structures & Algorithm",
          year: "3rd Semester"
        }]
      }
    },
    components: {
      Header,
      CardImg
    }
  }
</script>