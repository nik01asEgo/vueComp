<template>
  <div class="v_Main">
    <vCatalog></vCatalog>
  </div>
</template>

<script>
  import vCatalog from "./V_catalog.vue";
  export default {
    name: "v_main",
    components: {
      vCatalog
    },
    created() {},
    data() {
      return {};
    },
    props: {},
    methods: {},
  };
</script>

<style >
  .v_Main {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
  }
</style>