<template>
  <b-navbar id="chat-navbar" toggleable="md" type="dark" variant="info">
    <b-navbar-brand href="#">Vueture</b-navbar-brand>
    <b-navbar-nav class="ml-auto">
      <b-nav-text>{{ user.name }}</b-nav-text>
      <b-button variant="outline-danger" id="chat-logout" href="#" @click="onLogout">Logout</b-button>
    </b-navbar-nav>
  </b-navbar>
</template>

<script>
import { mapState, mapActions, mapMutations } from "vuex";

export default {
  name: "ChatNavBar",
  computed: {
    ...mapState(["user", "reconnect"])
  },
  methods: {
    ...mapActions(["logout", "login"]),
    ...mapMutations(["setReconnect"]),
    onLogout() {
      this.$router.push({ path: "/" });
      this.logout();
    },
    unload() {
      if (this.user.username) {
        // User hasn't logged out
        this.setReconnect(true);
      }
    }
  },
  mounted() {
    window.addEventListener("beforeunload", this.unload);
    if (this.reconnect) {
      this.login(this.user.username);
    }
  }
};
</script>

<style>
#chat-navbar {
  margin-bottom: 15px;
  background: #3494e6; /* fallback for old browsers */
  background: -webkit-linear-gradient(
    to right,
    #ec6ead,
    #3494e6
  ); /* Chrome 10-25, Safari 5.1-6 */
  background: linear-gradient(
    to right,
    #ec6ead,
    #3494e6
  ); /* W3C, IE 10+/ Edge, Firefox 16+, Chrome 26+, Opera 12+, Safari 7+ */
}

#chat-logout {
  color: white;
  border-color: #3494e6;
}
</style>