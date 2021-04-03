<template>
  <b-container fluid v-if="check()">
    <b-row>
      <b-col style="padding: 0">
        <h1 class="title2">Institutes that you are enrolled in</h1>
        <b-row v-for="sub in institutes" :key="sub" class="comp">
          <b-col md="6" cols="12">
            <CardImg  :src="sub.src" :name="sub.name" :sub1="sub.sub1" />
          </b-col>
          <b-col md="6" cols="12">
            <b-button class="subject-button" variant="danger">Leave
            </b-button>
            <b-button @click="changePage()" class="subject-button button" variant="outline-primary">View
            </b-button>
          </b-col>
        </b-row>
      </b-col>
    </b-row>
  </b-container>
</template>


<style scoped>
  .title2 {
    margin: 1em 1em 0;
    font-size: 2.1em;
    font-weight: bold;
  }

  .subject-button {
    margin: 2em 0.5em 0;
    border-radius: 0.5em;
    font-size: 1.4em;
    width: 30%;
    float: right;
  }

  

  @media (max-width: 768px) {

    .subject-button {
      margin: 0.5em;
      border-radius: 0.5em;
      font-size: 1em;
      width: 100%;
    }
  }
</style>


<script>
  import CardImg from "./Card-Img"


  export default {
    data() {
      return {
        view: true,
        institutes: [{
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
    computed: {
      groupFilter: function () {
        var final;
        this.items.forEach(item => {
          if (item.name == this.activeGroup) {
            final = item;
          } else {
            final = this.items[0]
          }
        });
        return final.content;
      }
    },
    components: {
      CardImg
    },
    methods: {
      changePage() {
        this.$emit("instituteView", ["InstituteView",false]);
        this.view = false;
      },
      check(){
        if(this.propView == "false"){
          return false
        }
        return this.view
      }
    },
    props:{
      propView: String
    }
  }
</script>