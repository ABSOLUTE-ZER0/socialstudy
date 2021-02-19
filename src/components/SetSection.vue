<template>
        <b-row>
      <b-col cols="3">
        <CheckBox :item="classes[0]" />
        <CheckBox :item="classes[0]" />
        <CheckBox :item="classes[0]" />
      </b-col>
      <b-col cols="3">
        <CheckBox :item="classes[0]" />
        <CheckBox :item="classes[0]" />
        <CheckBox :item="classes[0]" />
      </b-col>
      <b-col cols="3">
        <CheckBox :item="classes[1]" />
        <CheckBox :item="classes[1]" />
        <CheckBox :item="classes[1]" />
      </b-col>
      <b-col cols="3">
        <CheckBox :item="classes[1]" />
        <CheckBox :item="classes[1]" />
        <CheckBox :item="classes[1]" />
      </b-col>


    </b-row>
</template>










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