<template>
  <div>
    <b-input-group :class="className" >
      <template #append>
        <b-dropdown id="dropdown" menu-class="w-100" variant="info">
          <b-dropdown-item v-for="item in items" :key="item">{{item}}</b-dropdown-item>
        </b-dropdown>
      </template>
      <b-form-input v-if="!check()" class="input" type="text" :placeholder="placeHolder">
      </b-form-input>
      <b-form-textarea v-if="check()" class="input" :placeholder="placeHolder" no-resize rows="4">
        <b-form-input type="text">
        </b-form-input>
      </b-form-textarea>
    </b-input-group>
  </div>
</template>





<style scoped>
  .input {
    background-color: #EAFDFB;
    border: 0;
    margin: 1em 5% 0;
    margin-right: 0;
    border-radius: 0.5em;
    border-top-right-radius: 0;
    border-bottom-right-radius: 0;
    font-size: 1.5em;
  }

  .assignment>div {
    display: flexbox;
    margin-right: 5%;
    margin-top: 1.5em;
    border-top-right-radius: 0.5em;
    border-bottom-right-radius: 0.5em;
  }


</style>

<style>
  #dropdown>button{
    background-color: #EAFDFB;
    border: 0;
    color: black;
  }
</style>


<script>
  export default {
    data() {
      return {
      }
    },
    props: {
      items: Array,
      className: String,
      placeHolder: String,
      textarea: {
        type: Boolean,
        default: true
    },
  },
  methods:{
    check(){

      if(this.textarea == true){
        return true
      }
      else{
        return false
      }
    }
  }
  }
</script>