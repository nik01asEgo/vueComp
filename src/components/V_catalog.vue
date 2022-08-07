<template>
  <div class="v_catalog">
    <div v-if="isLoading">LOADING...</div>
    <div v-else class="v_catalog_text_conteiner">
      <h1>Кошки в Москве</h1>
      <p>
        На Kinpet нашлось 1 077 объявлений кошек в Москве, которые соответствуют вашим
        критериям. Подберите понравившегося питомца и свяжитесь с продавцом в два клика.
      </p>
    </div>
    <vCatalogItem v-for="item in cats" :key="item.article" :item_data="item" />
  </div>
</template>

<script>
import vCatalogItem from "@/components/V_catalog_item";
import { cats } from "@/static_store";

export default {
  name: "v_catalog",
  components: {
    vCatalogItem,
  },
  created() {},
  data() {
    return {
      cats: cats, //[],
      isLoading: false, //true,
    };
  },
  props: {},
  methods: {},
  // beforeMount() {
  //   (async () => {
  //     const result = await fetch("http://localhost:8081/cats.json");
  //     this.cats = result.body();
  //     this.isLoading = false;
  //   })();
  // },
};
</script>

<style>
.v_catalog {
  transition: 0, 5s;
  background-color: #f4f7f9;
  display: flex;
  flex-wrap: wrap;
  box-sizing: border-box;
  font-family: Montserrat, sans-serif;
}
.v_catalog_text_conteiner {
  text-align: left;
}
</style>
