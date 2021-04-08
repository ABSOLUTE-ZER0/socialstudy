<template>
  <div style="background-color: #f7f3f3; min-height: 100vh">
    <Header />
    <b-container fluid>

      <b-row>
        <h1 class="sub-title">{{item.title}}</h1>
        <b-button class="button upload-btn">Upload</b-button>
      </b-row>


      <b-row>

        <b-col lg="9">

          <b-row class="tab-row">
            <b-button @click="activeTab='RecordedLecture'" class="tab-button no-outline-button"
              v-bind:class="{'active-tab shadow': activeTab=='RecordedLecture'}">Recorded lecture</b-button>
            <b-button @click="activeTab='LiveClassRecording'" class="tab-button no-outline-button"
              v-bind:class="{'active-tab shadow': activeTab=='LiveClassRecording'}">Live class recording</b-button>
            <b-button @click="activeTab='Notes'" class="tab-button no-outline-button"
              v-bind:class="{'active-tab shadow': activeTab=='Notes'}">Notes</b-button>
            <b-button @click="activeTab='Assignment'" class="tab-button no-outline-button"
              v-bind:class="{'active-tab shadow': activeTab=='Assignment'}">Assignment</b-button>
            <b-button @click="activeTab='Question/Solution'" class="tab-button no-outline-button"
              v-bind:class="{'active-tab shadow': activeTab=='Question/Solution'}">Question/Solution</b-button>
          </b-row>




          <div v-if="activeTab=='RecordedLecture'">
            <div v-for="items in item2" :key="items" lg="9">
              <CardImg :src="items.src" class="comp card" :name="items.name" :sub1="items.year" />
            </div>
          </div>


          <div v-if="activeTab=='Notes'">
            <div v-for="items in item3" :key="items" lg="9">
              <CardImg :src="items.src" class="comp card" :name="items.name" :sub1="items.year" />
            </div>
          </div>


          <div v-if="activeTab=='Assignment'">
            <div v-for="items in item4" :key="items" lg="9">
              <CardImg :src="items.src" class="comp card" :name="items.name" :sub1="items.year" />
            </div>
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
  .comp.card {
    padding: 0.5em 2em 1em;
  }

  .filter {
    padding: 1em;
  }


  .tab-row {
    border-bottom: 2px solid rgb(117, 117, 117);
    margin-bottom: 1em;
    margin-left: 0;
    margin-right: 10px;
    display: flex;
  }


  .tab-button {
    margin: 0.5em 0 0;
    font-size: 1.5em;
    flex: 1;
    text-align: center;
    color: rgb(117, 117, 117) !important;
  }

  button.active-tab.tab-button {
    background-color: rgb(117, 117, 117) !important;
    color: white !important;
    border-radius: 0.5em;
    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
  }

  .tab-button:hover {
    color: white !important;
    background-color: rgb(148, 148, 148) !important;
    box-shadow: none !important;
    border-radius: 0.5em;

    border-bottom-left-radius: 0;
    border-bottom-right-radius: 0;
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
</style>

<style>
  .filters>div>div>label {
    line-height: 1.8em;
    margin-top: 0.2em;
  }
</style>







<script>
  import Header from "../components/Header";
  import CardImg from "../components/Card-Img"




  export default {

    data() {
      return {
        activeTab: "RecordedLecture",
        options: [{
            text: 'All',
            value: 'all'
          },
          {
            text: 'Algebra',
            value: 'algebra'
          },
          {
            text: 'Set Theory',
            value: 'sets'
          },
          {
            text: 'Trigonometry',
            value: 'trigonometry'
          }
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
        }],
        item3: [{
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Data Structures & Algorithm",
          year: "3rd Semester"
        }, {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Data Structures & Algorithm",
          year: "3rd Semester"
        }],
        item4: [{
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Data Structures & Algorithm",
          year: "3rd Semester"
        }, {
          src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
          name: "Data Structures & Algorithm",
          year: "3rd Semester"
        }],
      }
    },
    components: {
      Header,
      CardImg
    }
  }
</script>