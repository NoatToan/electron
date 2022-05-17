<template>
  <div class="container">
    <img src="/nuxt.png" />
    <h2>Profile Print Process</h2>
    <div>
      <div>
        <h3>{{ status == 1 ? "Tap button for connecting device..." : "Connected!" }}</h3>
        <button @click="connectDevice()">Connect</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  asyncData({ req }) {
    return {
      // 1: Connecting, 2. Connected
      status: 1,
    };
  },
  methods: {
    connectDevice() {
      this.status = 2;
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
