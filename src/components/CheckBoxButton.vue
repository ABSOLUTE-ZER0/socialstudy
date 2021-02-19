<template>
  <div class="checkboxdiv" >
    <label :id="item.id" @click="setId(item.id);selected" for="df" class="checkbox-text">{{item.name}}<br>{{item.year}} {{item.branch}}<br>{{item.section}}</label>
  </div>

</template>

<style scoped>
  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
    white-space: pre-wrap;
    position: relative;
  }

  .checkboxdiv{
    width: 90%;
    margin: 5%;
  }

  .active{
    background-color: cyan;
    color: black !important;
  }

  .checkBox{
    position: relative;
    top: 50%;
  }

  .checkbox-text {
    padding: 1em;
    margin: 2%;
    border: 2px solid rgb(179, 179, 179);
    color: rgb(0, 201, 201);
    font-size: 1.3em;
    font-weight: bold;
    border-radius: 1em;
    width: 100%;
  }
</style>

<script>
export default {
  data(){
    return{
      classid: 0,
    }
  },
  methods:{
    setId(id){
      this.classid = id
      var ele = document.getElementById(this.classid);
      var all = document.getElementsByClassName("active");
      all.forEach(i => {
      i.classList.remove('active');
      });
      ele.classList.toggle('active');
    }
  },
  props:{
    item: Object
  }
}
</script>