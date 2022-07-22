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
   
}
.vContaner {
  display: grid;
  grid-template-areas:
    'header header'
    'main navigation'
    'footer footer';
  grid-gap: 10px;
  grid-template-columns: 1fr 315px;
  grid-template-rows: 100px 1fr 100px;  
}
.vHeader {
 grid-area: header;
 border: 1px solid #2c3e50;
}
.vMain {
   grid-area: main;
   border: 1px solid #2c3e50;
}
@media screen  and (max-width: 1450px) { 
  .vContaner {
    grid-template-areas:
    'header header'
    'main main'
    'footer footer';
    width: 100%;
 }
}
.vNavigation {
   grid-area: navigation;
   border: 1px solid #2c3e50;
   align-self: start;

}
.vFooter {
   grid-area: footer;
   border: 1px solid #2c3e50;
}
</style>
