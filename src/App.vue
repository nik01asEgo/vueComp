<template>
  <div class="vContaner">
    <vHeader class="vHeader" />
    <div id="v-portal-modal" />
    <vMain class="vMain" />
    <vNavigation class="vNavigation" />
    <vFooter class="vFooter" />
  </div>
</template>

<script>
import vHeader from "./components/V_header.vue";
import vMain from "./components/V_main.vue";
import vNavigation from "./components/V_Navigation.vue";
import vFooter from "./components/V_footer.vue";

export default {
  name: "App",
  components: {
    vHeader,
    vMain,
    vNavigation,
    vFooter,
  },
};
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
    "header header"
    "main navigation"
    "footer footer";
  grid-gap: 10px;
  grid-template-rows: 100px 1fr 100px;
  grid-template-columns: 1fr;
  margin-left: 180px;
  margin-right: 180px;
}
.vHeader {
  width: 100%;
  height: 100px;
  grid-area: header;
  position: fixed;
  top: 0px;
  left: 0px;

  z-index: 15;
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
    width: stretch;
  }
}
@media screen and (max-width: 1550px) {
  .v_Navigation {
    width: 325px;
  }
}
@media screen and (min-width: 1240px) and (max-width: 1450px) {
  .v_Navigation {
    display: none;
  }
  .vContaner {
    width: 1050px;
  }
}
@media screen and (min-width: 1160px) and (max-width: 1240px) {
  .vContaner {
    width: 1050px;
    margin-left: 50px;
    margin-right: 50px;
  }
  .v_Navigation {
    display: none;
  }
}
@media screen and (max-width: 1160px) {
  .vContaner {
    margin-left: 50px;
    margin-right: 50px;
  }
  .v_Navigation {
    display: none;
  }
}
@media screen and (max-width: 1000px) {
  .vContaner {
    margin-left: 20px;
    margin-right: 20px;
  }
}
@media screen and (min-width: 731px) and (max-width: 860px) {
  .vContaner {
    width: 691px;
  }
}
</style>
