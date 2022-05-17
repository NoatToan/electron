<template>
  <div class="container">
    <img src="/nuxt.png" />
    <h2>Hello Nuxtron.</h2>
    <p>Loaded from the {{ name }}</p>
    <div>
      <div>
        <label> Username </label>
        <input v-model="auth.user_name" type="text" />
      </div>
      <div>
        <label> Password </label>
        <input v-model="auth.password" type="password" />
      </div>
      <button type="submit" @click="login()">Login</button>
    </div>
  </div>
</template>

<script>
export default {
  asyncData({ req }) {
    return {
      name: process.static ? "static" : process.server ? "server" : "client",
      auth: {
        user_name: "",
        password: "",
      },
    };
  },
  methods: {
    login() {
      if (this.auth.user_name == "123123" && this.auth.password == "123123") {
        this.$router.push({ name: "profilePrint" });
      }
    },
  },
};
</script>

<style scoped>
.container {
  position: absolute;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  background: white;
  color: black;
  font-family: "Lucida Console", Monaco, monospace;
  padding-top: 100px;
  text-align: center;
}
a {
  color: black;
}
</style>
