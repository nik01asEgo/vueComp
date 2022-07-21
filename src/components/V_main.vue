<template>
  <div>
    <p>{{ title }}</p>
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
      return {
        title: 'i am main'
      };
    },
    props: {},
    methods: {},
  };
</script>

<style lang="scss" scoped></style>