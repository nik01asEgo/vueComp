<template>
  <div class= "vContaner">
    <vHeader class="vHeader"></vHeader>
    <vMain class="vMain"></vMain>
    <vNavigation class="vNavigation"></vNavigation>
    <vFooter class="vFooter"></vFooter>
  </div>
</template>

<script>
  import vHeader from "./components/V_header.vue";
  import vMain from "./components/V_main.vue";
  import vNavigation from "./components/V_Navigation.vue";
  import vFooter from "./components/V_footer.vue";

export default {
  name: 'App',
  components: {
    vHeader,
    vMain,
    vNavigation,
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
  background-color: #f4f7f9;
   
}
.vContaner {
  display: grid;
  grid-template-areas:
    'header header'
    'main navigation'
    'footer footer';
  grid-gap: 10px;
  grid-template-rows: 100px 1fr 100px;  
  /* min-width: 1550px; */
  margin-left: 90px;
  margin-right: 90px;
}
.vHeader {
  grid-area: header;
}
.vMain {
  grid-area: main;
}
.vNavigation {
  grid-area: navigation;
  align-self: start;
  border-radius: 4px;
  width: 365px;
}
.vFooter {
  grid-area: footer;
  border: 1px solid #2c3e50;
}
@media screen and (max-width: 1770px) {
  .vContaner {
  margin-left: 90px;
  margin-right: 90px;
  width: fill-available;
 
  }
}
@media screen and (max-width: 1550px) {
  .v_Navigation {
    width: 325px;
  } 
}
@media screen and (max-width: 1450px) { 
  .v_Navigation {
    display: none;
  }
  .vContaner {
    width: 1000px;
  }
}
@media screen and (max-width: 1270px) {
  .vContaner {
    margin-left: 50px;
    margin-right: 50px;
  }
}
@media screen and (max-width: 1100px) {
  .vContaner {
    width: calc(100%-100px);
    margin-left: 50px;
    margin-right: 50px;

  }
}

</style>
