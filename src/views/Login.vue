<template>
  <div class="login">
    <b-jumbotron
      id="jumbotron"
      header="Vueture"
      lead="Powered by Chatkit SDK and Vue"
      bg-variant="info"
      text-variant="white"
    >
      <p>Under development...</p>
      <b-btn target="_blank" href="https://github.com/FredAmartey/Vueture">GitHub</b-btn>
    </b-jumbotron>
    <b-container>
      <b-row>
        <b-col lg="4" md="3"></b-col>
        <b-col lg="4" md="6">
          <LoginForm />
        </b-col>
        <b-col lg="4" md="3"></b-col>
      </b-row>
    </b-container>
    <b-navbar id="psuedo-footer" type="light" variant="light">
      <a href="https://fredamartey.com" target="_blank">
        <img class="fa-logo" src="../assets/fred-logo-complete-grey.png" />
      </a>
    </b-navbar>
  </div>
</template>

<script>
import LoginForm from "@/components/LoginForm.vue";

export default {
  name: "login",
  components: {
    LoginForm
  }
};
</script>

<style>
#jumbotron {
  background-color: #3494e6 !important; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #ec6ead,
    #3494e6
  ) !important; /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #ec6ead,
    #3494e6
  ) !important; /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

#psuedo-footer {
  margin-bottom: 30px !important;
  padding: 0 !important;
  background-color: transparent !important;
  position: fixed;
  left: 0;
  bottom: 0;
  width: 100%;
  display: inline-block;
  text-align: center !important;
}

.fa-logo {
  display: inline-block;
  vertical-align: middle;
  max-width: 180px;
}
</style>