<template>
        <b-row class="class-row">
      <b-col class="class-col" cols="3">
        <CheckBox :item="classes[0]" />
        <CheckBox :item="classes[0]" />
        <CheckBox :item="classes[0]" />
      </b-col>
      <b-col class="class-col" cols="3">
        <CheckBox :item="classes[0]" />
        <CheckBox :item="classes[0]" />
        <CheckBox :item="classes[0]" />
      </b-col>
      <b-col class="class-col" cols="3">
        <CheckBox :item="classes[1]" />
        <CheckBox :item="classes[1]" />
        <CheckBox :item="classes[1]" />
      </b-col>
      <b-col class="class-col" cols="3">
        <CheckBox :item="classes[1]" />
        <CheckBox :item="classes[1]" />
        <CheckBox :item="classes[1]" />
      </b-col>


    </b-row>
</template>

<style scoped>
    @media (max-width: 768px){
      .class-col{
        padding: 0;
      }
      .class-row{
        margin: 1em;
      }
    }
</style>








<script>
  import CheckBox from "./CheckBoxButton"
  export default {
    data() {
      return {
        siteName: "",
        classes: [{
            id: "1",
            name: "Friends Name",
            year: "year",
            brach: "IT",
            section: "Section A",
          },
          {
            id: "2",
            name: "Friends Name",
            year: "year",
            brach: "CS",
            section: "Section B",
          }

        ]
      }
    },
    components: {
      CheckBox
    },
    methods: {

    }
  }
</script>