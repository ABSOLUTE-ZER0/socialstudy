<template>
  <div class="main-div">
    <b-container fluid>
      <b-row >
        <h1>socialstudy</h1>
      </b-row>

      <b-row>
        <b-col lg="6" class="col1 d-none d-lg-block">

          <h3><i class="fas fa-user"></i> Maintain your academic profile</h3>
          <h3><i class="fas fa-user-plus"></i> Connect with faculty and friends</h3>
          <h3><i class="fas fa-book-open"></i> Access to study materials </h3>
          <img class="home-img" src="../assets/dummy-image.jpg">
        </b-col>

        <b-col lg="6">
          <h2 style="margin-top: -1em">Join your Academic Community</h2>
          <b-form>
            <b-form-group>
              <b-form-input class="home-input" type="text" placeholder="Username"></b-form-input>
            </b-form-group>

            <b-form-group class="password-form">
              <b-form-input class="home-input" type="password" placeholder="Password"></b-form-input>
              <a class="home-forgot-password" href="#">Forgot Password</a>
            </b-form-group>
            <b-button class="home-btn" href="/home" type="submit" variant="info">Log In</b-button>
            <b-button class="home-btn" href="" variant="outline-primary" @click="openRegisterModal">Create New Account
            </b-button>
          </b-form>
        </b-col>
      </b-row>

    </b-container>
    <div v-if="registerModalDiv">
      <div class="modal-mask registerModal">
        <div class="modal-wrapper">
          <div class="modal-dialog">
            <div class="modal-content">
              <div v-if="registerModal1" class="modal-dialog">
                <div class="modal-header">
                  <h1 class="register-title">Fill Your Basic Details</h1>
                </div>
                <b-form>
                  <div class="inline-form">
                    <b-form-input class="home-input small" type="text" placeholder="First Name"></b-form-input>
                    <b-form-input class="home-input small" type="text" placeholder="Last Name"></b-form-input>
                  </div>
                  <b-form-group>
                    <b-form-input class="home-input" type="email" placeholder="Email"></b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="home-input" type="password" placeholder="Password"></b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="home-input" type="text" placeholder="Date of Birth"></b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="home-input" type="text" placeholder="User type - student/teacher/admin">
                    </b-form-input>
                  </b-form-group>
                  <b-button style="margin-left: 70%" class="register-btn" href="" variant="info"
                    @click="registerModal1=false;registerModal2=true">Next</b-button>
                </b-form>

              </div>



              <div v-if="registerModal2" class="modal-dialog">
                <div class="modal-header">
                  <h1 class="register-title">Current Education Details</h1>
                </div>
                <b-form>
                  <div class="inline-form">
                    <b-form-input class="home-input small" type="text" placeholder="County"></b-form-input>
                    <b-form-input class="home-input small" type="text" placeholder="State"></b-form-input>
                  </div>
                  <b-form-group>
                    <b-form-input class="home-input" type="text" placeholder="City"></b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="home-input" type="text" placeholder="Institute Category"></b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="home-input" type="text" placeholder="Institute Category"></b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="home-input" type="text" placeholder="Course"></b-form-input>
                  </b-form-group>
                  <b-form-group>
                    <b-form-input class="home-input" type="text" placeholder="Specialization"></b-form-input>
                  </b-form-group>
                  <b-button style="margin-left: 25%" class="register-btn" href="" variant="info"
                    @click="registerModal1=true;registerModal2=false">Back</b-button>
                  <b-button class="register-btn" href="/home" variant="info"
                    @click="registerModalDiv=false;registerModal1=false;registerModal2=false;">Register</b-button>
                </b-form>

              </div>

            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>


<style>
  body {
    background-color: white;
  }
</style>



<style scoped>
  .main-div {
    margin: 4%;
    margin-left: 7%;
    margin-top: 0;
    color: rgb(0, 202, 202);
  }

  h1 {
    font-size: 4em;
    margin-top: 4%;
    margin-bottom: 1.5em;
  }

  .register-title {
    margin-bottom: 2%;
  }

  h3 {
    margin-top: 1.5em;
    color: rgb(153, 153, 153);
  }

  h2 {
    font-size: 3em;
    margin-top: 20%;
    margin-bottom: 1.5em;
  }

  .col1 {
    text-align: left;

  }

  .home-img {
    width: 80%;
  }

  .home-btn {
    width: 80%;
    border-radius: 4em;
    font-size: 2em;
    margin: 0.2em 0;
  }

  .home-input {
    background-color: rgba(127, 255, 212, 0.175);
    border: 0;
    margin-left: 10%;
    margin-bottom: 0.7rem;
    border-radius: 0.5em;
    font-size: 1.5em;
    width: 80%;
  }

  .home-input.small {
    width: 35%;
    margin-top: 5%;
    margin-bottom: 1.4rem;
  }


  .password-form {
    text-align: left;

  }

  .home-forgot-password {
    color: rgb(0, 204, 255);
    margin-left: 15%;
    font-weight: 200;

  }

  .form-group {
    margin-bottom: 0.5rem !important;

  }

  .inline-form {
    width: 100%;

    display: flex;
    flex-flow: row wrap;
    align-items: center;
  }

      .registerModal {
    position: fixed;
    z-index: 2;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .5);
    display: table;
    transition: opacity .3s ease;
  }

      .modal-dialog {
    pointer-events: all !important;
    max-width: none !important;
    min-width: 100% !important;
  }

  .modal-wrapper {
    display: table-cell;
    vertical-align: middle;

  }

  .modal-content {
    width: 100%;
  }

  .register-btn {
    margin: 5%;
    margin-top: 0;
    width: 20%;
  }

  .modal-header {
    display: inline-block;
    min-width: 100%;
  }

    @media (max-width: 992px) and (min-width: 768px) {
    .main-div {
      text-align: center;
    }
    }

    
    @media (max-width: 768px) {
    .main-div {
      text-align: center;
    } 
    h1{
      font-size: 3em;

    }
    h2{
      font-size: 2em;
          margin-top: 10% !important;
    margin-bottom: 1.5em;
    }
      .register-btn {
        width: 30%;
    border-radius: 1em;
    margin: 1em;
    margin-left: 1.5em !important;
  }
  .register-title{
    font-size: 2em;
  }
  }
</style>


<script>
  export default {
    data() {
      return {
        registerModalDiv: false,
        registerModal1: false,
        registerModal2: false
      }
    },
    methods: {
      openRegisterModal() {
        this.registerModalDiv = true;
        this.registerModal1 = true;
      }
    }
  }
</script>