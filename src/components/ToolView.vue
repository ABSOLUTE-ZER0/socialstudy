<template>

  <div>

    <div v-if="displayModalGroupCreate">
      <div class="modal-mask createpostModal">
        <div class="modal-wrapper ">
          <div class="modal-dialog">
            <div class="modal-content">
              <b-icon @click="displayModalGroupCreate=false" class="exit-modal" icon="x"></b-icon>

              <h1 class="title shadow-none"><i class="far fa-edit"></i> Create Assignment</h1>
              <b-form>
                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="Group Name"></b-form-input>
                </b-form-group>
                <b-form-group>
                  <b-form-select class="input" v-model="selectedSubject" :options="optionsGroup"></b-form-select>
                </b-form-group>
                <b-form-group>
                  <b-form-input class="input" type="text" placeholder="Description"></b-form-input>
                </b-form-group>
                <b-button style="margin-left: 70%" class="post-btn" variant="info"
                  @click="displayModalGroupCreate=false">Submit</b-button>
              </b-form>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div class="comp" v-if="pageName=='StartLiveClass'">
      <b-row>
        <b-col cols="9">
          <b-button style="margin-left: 10%" class="assignment-btn " variant="outline-info">Start Live Class</b-button>
          <b-button @click="displayModalGroupCreate=true" class="assignment-btn " variant="info">+ Create Group
          </b-button>
        </b-col>
        <b-col class="filter-col" cols="3">
          <b-navbar>
            <b-navbar-nav>
              <b-nav-item class="filter">
                <i class="fas fa-2x icon fa-clipboard-check"></i> Select Filter
              </b-nav-item>
            </b-navbar-nav>
          </b-navbar>
        </b-col>
      </b-row>
      <b-row>
        <p style="margin-left: 10%">Select group to start live classes</p>
        <p style="margin-left: 10%">Below active background is not a bug ,once you give different id's for different
          sections it will work properly</p>
      </b-row>
    </div>



    <div class="comp" v-if="pageName=='FileSharing'">
      <b-row>
        <b-col cols="9">
          <b-button style="margin-left: 10%" class="assignment-btn " variant="outline-info">+ Upload File</b-button>
          <b-button @click="displayModalGroupCreate=true" class="assignment-btn " variant="info">+ Create Group
          </b-button>
        </b-col>
        <b-col class="filter-col" cols="3">
          <b-navbar>
            <b-navbar-nav>
              <b-nav-item class="filter">
                <i class="fas fa-2x icon fa-clipboard-check"></i> Select Filter
              </b-nav-item>
            </b-navbar-nav>
          </b-navbar>
        </b-col>
      </b-row>
      <b-row>
        <p style="margin-left: 10%">Select group to start live classes</p>
        <p style="margin-left: 10%">Below active background is not a bug ,once you give different id's for different
          sections it will work properly</p>
      </b-row>
    </div>

    <div v-if="pageName=='Assignment'">
      <div class="comp">
        <b-row>
          <b-col cols="9">
            <b-button @click="displayModalAssignment=true" style="margin-left: 10%" class="assignment-btn"
              variant="outline-info">+ Create Assignment
            </b-button>
          </b-col>
          <b-col class="filter-col" cols="3">
            <b-navbar>
              <b-navbar-nav>
                <b-nav-item class="filter">
                  <i class="fas fa-2x icon fa-clipboard-check"></i> Select Filter
                </b-nav-item>
              </b-navbar-nav>
            </b-navbar>
          </b-col>
        </b-row>
        <b-row>
        </b-row>
      </div>

      <div v-for="item in items" :key="item" class="comp">
        <b-row>
          <b-col cols="6" md="8">
            <CardImg3 :src="item.src" :name="item.name" :sub2="item.subject" :sub1="item.group" />
          </b-col>
          <b-col cols="6" md="4">
            <b-button class="button assignment-button" variant="info">Edit
            </b-button>
            <b-button class="button assignment-button" variant="danger">Delete
            </b-button>
          </b-col>
        </b-row>
      </div>

      <div v-if="displayModalAssignment">
        <div class="modal-mask createpostModal">
          <div class="modal-wrapper ">
            <div class="modal-dialog">
              <div class="modal-content">
                <b-icon @click="displayModalAssignment=false" class="exit-modal" icon="x"></b-icon>

                <h1 class="title shadow-none"><i class="far fa-edit"></i> Create Assignment</h1>
                <b-form>
                  <b-form-group>
                                      <b-form-select class="input" v-model="selectedAssignGroup" :options="optionsAssignGroup"></b-form-select>
                  </b-form-group>
                  <b-form-group>
                                      <b-form-select class="input" v-model="selectedAssignSubject" :options="optionsAssignSubject"></b-form-select>
                  </b-form-group>
                  <b-form-group>
                                      <b-form-select class="input" v-model="selectedAssignType" :options="optionsAssignType"></b-form-select>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="input" type="text" placeholder="Heading"></b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="input" type="text" placeholder="Description"></b-form-input>
                  </b-form-group>
                  <b-button style="margin-left: 70%" class="post-btn" variant="info"
                    @click="displayModalAssignment=false">Submit</b-button>
                </b-form>
              </div>
            </div>
          </div>
        </div>
      </div>

    </div>


    <div v-if="pageName=='Attendance'" class="comp">
      <h3 class="attendance-title">Attendance</h3>
      <div class="attendance-table">
        <b-table striped hover :items="attendance" :fields="fields"></b-table>

      </div>

      <h4 class="avg-att-title">Overall Average Attendance</h4>
      <div id="chart">
        <apexchart type="pie" width="380" :options="chartOptions" :series="series"></apexchart>
      </div>

    </div>

    <div class="comp" v-if="pageName=='StartLiveClass' || pageName=='FileSharing' || pageName=='ManageGroup'">
      <SetSection />
    </div>



  </div>

</template>


<style scoped>
  .comp {
    white-space: pre-wrap;
  }

  .filter {
    text-align: center;
    font-weight: bold;
    font-size: 1.2em;

  }

  .con-btn {
    margin: 1em;
    width: 20%;
    border-radius: 1em;
    font-size: 2em;
  }


  .assignment-button {
    margin: 2.5em 0.5em;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 40%;
  }

  .assignment-btn {
    margin: 1.5em;
    width: 30%;
    border-radius: 1em;
    font-size: 1.5em;
  }

  .attendance-title {
    padding: 1em 2em;
  }

  .attendance-table {
    margin: 0 5%;
  }

  .avg-att-title {
    margin: 2em;
  }

  #chart {
    margin-left: 20%;
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
        border-radius: 2em;

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
    .assignment-btn {
      margin: 1em !important;
      width: 40%;
      border-radius: 1em;
      font-size: 1.2em;
    }

    .filter-col {
      padding: 0;
      margin-left: -2em;
      width: 100%;
    }

    .navbar {
      padding: 0;
    }

    .gone {
      display: none;
    }

    .assignment-btn {
      width: fit-content;
    }

    .assignment-button {
      margin: 2em 0.125em;
      border-radius: 0.5em;
      font-size: 1.4em;
      width: 40%;
    }

    .attendance-title {
      font-size: 2em;
    }

    .attendance-table {
      margin: 1em;
    }
  }
</style>



<script>
  import SetSection from "./SetSection"
  import CardImg3 from "./Card-Img-3"
  import VueApexCharts from 'vue-apexcharts'

  export default {
    data() {
      return {
        siteName: "",
        selectedSubject: null,
        selectedAssignGroup: null,
        selectedAssignSubject: null,
        selectedAssignType: null,
        displayModalAssignment: false,
        displayModalGroupCreate: false,
        series: [82, 18],
        chartOptions: {
          chart: {
            width: 380,
            type: 'pie',
          },
          labels: ['Present', 'Abscent'],
          responsive: [{
            breakpoint: 480,
            options: {
              chart: {
                width: 200
              },
              legend: {
                position: 'bottom'
              }
            }
          }]
        },


        fields: ['Subject_Month', 'July', 'August', 'September', 'October', 'November'],
        attendance: [{
            isActive: true,
            Subject_Month: "Data Structures",
            July: "78%",
            August: "70%",
            September: '80%',
            October: '76%',
            November: '68%'
          },
          {
            isActive: true,
            Subject_Month: "Operating Systems",
            July: "78%",
            August: "70%",
            September: '80%',
            October: '76%',
            November: '68%'
          }
        ],
        items: [{
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Sample Assignment 1",
            group: "Assigned group",
            subject: "Subject",
          },
          {
            src: "https://image.shutterstock.com/image-photo/large-beautiful-drops-transparent-rain-600w-668593321.jpg",
            name: "Sample Assignment 2",
            group: "Assigned group",
            subject: "Subject",
          }
        ],
        optionsGroup: [
          { value: null, text: "+ Subject/Topic", disabled: true },
          { value: '1', text: 'Item 1' },
          { value: '2', text: 'Item 2' },
          { value: '3', text: 'Item 3' },
          { value: '4', text: 'Item 4' }
        ],
        optionsAssignGroup: [
          { value: null, text: "+ Select Group", disabled: true },
          { value: '1', text: 'Item 1' },
          { value: '2', text: 'Item 2' },
          { value: '3', text: 'Item 3' },
          { value: '4', text: 'Item 4' }
        ],
        optionsAssignSubject: [
          { value: null, text: "+ Subject/Topic", disabled: true },
          { value: '1', text: 'Item 1' },
          { value: '2', text: 'Item 2' },
          { value: '3', text: 'Item 3' },
          { value: '4', text: 'Item 4' }
        ],
        optionsAssignType: [
          { value: null, text: "+ Type (Assignment/MCQ)", disabled: true },
          { value: '1', text: 'Item 1' },
          { value: '2', text: 'Item 2' },
          { value: '3', text: 'Item 3' },
          { value: '4', text: 'Item 4' }
        ],
      }
    },
    components: {
      SetSection,
      CardImg3,
      apexchart: VueApexCharts
    },
    methods: {

    },
    props: {
      pageName: String
    }
  }
</script>