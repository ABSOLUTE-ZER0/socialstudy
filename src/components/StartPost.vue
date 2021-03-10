<template>
  <b-row class="comp">
    <b-input-group class="startpost-div mb-2" size="sm">
      <b-input-group-prepend is-text>
        <i class="far fa-edit"></i>
      </b-input-group-prepend>
      <b-form-input class="startpost" type="search" placeholder="Start a post"></b-form-input>
    </b-input-group>
    <b-col class="p-div">
      <p class="p"><i class="fas fa-image"></i> Photo</p>
    </b-col>
    <b-col class="p-div">
      <p class="p"><i class="fab fa-youtube"></i> Video</p>
    </b-col>
    <b-col class="p-div">
      <p class="p"><i class="fab fa-wpforms"></i> Form</p>

    </b-col>
    <b-col class="p-div">
      <p class="p"><i class="far fa-newspaper"></i> Write article</p>
    </b-col>
  </b-row>
</template>

<style scoped>
  .p-div {
    text-align: center;
    font-size: 1.3em;
    cursor: pointer;
  }



  .startpost {
    height: 100% !important;
    border-top-right-radius: 2em !important;
    border-bottom-right-radius: 2em !important;
  }

  .startpost-div {
    margin: 2em 5em !important;
    height: 3em !important;
    width: 100%;
  }


  .comp {
    background-color: white !important;
    border-radius: 2em;
    margin: 1em;
  }

  @media (max-width: 768px) {
    .startpost-div {
      margin: 1em 2em !important;
    }

      .fa-edit {
                font-size: 0.7em;

  }

  .startpost{
        font-size: 1.3em !important;

  }



    .p {
      margin: 0 0 1em;
    }

    .p-div {
      padding: 0;
    }
  }
</style>