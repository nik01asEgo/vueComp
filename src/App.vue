<template>
  <div>
    <vHeader></vHeader>
    <vMain></vMain>
    <vFooter></vFooter>
  </div>
</template>

<script>
  import vHeader from "./components/V_header.vue";
  import vMain from "./components/V_main.vue";
  import vFooter from "./components/V_footer.vue";

export default {
  name: 'App',
  components: {
    vHeader,
    vMain,
    vFooter
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
