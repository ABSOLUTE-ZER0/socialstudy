<template>
  <div class="main-div">
    <b-container fluid>
      <b-row>
        <b-col>
          <h1 class="title">socialstudy</h1>
        </b-col>
      </b-row>

      <b-row>
        <b-col lg="6" class="col1 d-none d-lg-block">

          <h3><i class="fas fa-user"></i> Maintain your academic profile</h3>
          <h3><i class="fas fa-user-plus"></i> Connect with faculty and friends</h3>
          <h3><i class="fas fa-book-open"></i> Access to study materials </h3>
          <img class="home-img" src="../assets/dummy-image.jpg">
        </b-col>

        <b-col offset-lg="1" lg="5">
          <div class="input-col">
            <h2>Join your Academic Community</h2>
            <b-form>
              <b-form-group>
                <b-form-input class="home-input-main" type="text" placeholder="Username"></b-form-input>
              </b-form-group>

              <b-form-group class="password-form">
                <b-form-input class="home-input-main" type="password" placeholder="Password"></b-form-input>
                <a class="home-forgot-password" href="#">Forgot Password</a>
              </b-form-group>
              <b-button class="home-btn" href="/home" type="submit" variant="info">Log In</b-button>
              <b-button class="home-btn" href="" variant="outline-primary" @click="openRegisterModal">Create New Account
              </b-button>
            </b-form>
          </div>

        </b-col>
      </b-row>

    </b-container>
    <div v-if="registerModalDiv">
      <div class="modal-mask registerModal">
        <div class="modal-wrapper ">
          <div class="modal-dialog">
            <div class="modal-content">
              <div v-if="registerModal1" class="modal-dialog">
                <b-icon @click="closeRegisterModal" class="exit-modal" icon="x"></b-icon>
                <div class="modal-header">
                  <h1 class="register-title">Fill Your Basic Details</h1>
                </div>
                <b-form>
                  <div class="inline-form">
                    <b-form-input class="home-input small1" type="text" placeholder="First Name"></b-form-input>
                    <b-form-input class="home-input small2" type="text" placeholder="Last Name"></b-form-input>
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
                <b-icon @click="closeRegisterModal" class="exit-modal" icon="x"></b-icon>

                <div class="modal-header">
                  <h1 class="register-title">Current Education Details</h1>
                </div>
                <b-form>
                  <div class="inline-form">
                    <b-form-input class="home-input small1" type="text" placeholder="County"></b-form-input>
                    <b-form-input class="home-input small2" type="text" placeholder="State"></b-form-input>
                  </div>
                  <b-form-group>
                    <b-form-input class="home-input" type="text" placeholder="City"></b-form-input>
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

  .input-col {
    position: absolute;
    top: 50%;
    -ms-transform: translateY(-50%);
    transform: translateY(-50%);
    width: 100%;
  }

  h1, .title {
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
    font-size: 2.2em;
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
    border-radius: 1.5em;
    font-size: 1.5em;
    margin: 0.2em 0;
  }

  .home-input {
    background-color: rgba(127, 255, 212, 0.175);
    border: 0;
    margin-bottom: 0.7rem;
    border-radius: 0.5em;
    font-size: 1.5em;
    width: 100%;
  }

  .home-input-main{
    background-color: rgba(127, 255, 212, 0.175);
    border: 0;
    margin-bottom: 0.7rem;
    border-radius: 0.5em;
    font-size: 1.5em;
    width: 80%;
  }

  .home-input.small1,
  .home-input.small2 {
    width: 45%;
    margin-top: 5%;
    margin-bottom: 1.4rem;
  }

  .home-input.small2 {
    margin-left: 10%;
  }


  .password-form {
    text-align: left;

  }

  .home-forgot-password {
    color: rgb(0, 204, 255);
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

  .exit-modal{
    color: red;
    font-size: 2.5em;
    position: absolute;
    top: 0.5em;
    right: 0.5em;
  }

  @media (max-width: 992px) and (min-width: 768px) {
    .main-div {
      text-align: center;
    }
  }


  @media (max-width: 768px) {
    .input-col{
      position: relative;
    }
    .main-div {
      text-align: center;
      min-height: 100vh;
      background-image: url("../assets/background.jpg");
            margin: 0;

      color: rgb(0, 0, 0);

    }

      .home-btn {
    font-size: 1.8em;
  }
   

    .home-input-main{
    margin-left: 10%;
        background-color: rgba(168, 249, 255, 0.603);

  }

    .home-forgot-password {
    margin-left: 10%;
    font-size: 1.3em;
    color: black;
  }

    .modal-content {
    width: 100%;
    margin-left: 0;
  }

    .title {
      font-size: 4em;
      margin-top: 30%;
      font-family: fantasy;
      letter-spacing: 2px;
          text-shadow: 2px 2px rgb(204, 204, 204);

    }



    h2 {
      font-size: 2em;
      margin-top: 10% !important;
      margin-bottom: 1.5em;
      font-weight: bold ;
    }

    .register-btn {
      width: 40%;
      border-radius: 1em;
      margin: 1em;
      margin-left: 0em !important;
      font-size: 2em;
    }

    .register-title {
      font-size: 2.3em;
      font-weight: bold;

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
      },
      closeRegisterModal() {
        this.registerModalDiv = false;
        this.registerModal1 = false;
        this.registerModal2 = false;
      }
    }
  }
</script>