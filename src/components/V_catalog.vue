<template>
  <div class="v_catalog">
   
    <vCatalogItem 
      v-for= "item in cats"
      :key= "item.article"
      :item_data= "item"
      >
    </vCatalogItem>
  </div>
</template>

<script>
  import vCatalogItem from './V_catalog_item.vue';
  export default {
    name: "v_catalog",
    components: {
      vCatalogItem
    },
    created() {},
    data() {
      return {
       cats: [
          {
          image: "1.webp",
          name: "Мейн кун",
          city: "Москва",
          price: "80 Р",
          owner: "Вероника",
          article: "c1",
          available: true
          },
          {
          image: "2.webp",
          name: "Продажа",
          city: "Москва",
          price: "40000 Р",
          owner: "Татьяна",
          article: "c2",
          available: true
          },
          {
          image: "3.webp",
          name: "Продажа",
          city: "Москва",
          price: "40000 Р",
          owner: "Татьяна",
          article: "c3",
          available: true
          },
          {
          image: "4.webp",
          name: "3,5 мес принцесса Мура ищет семью!",
          city: "Москва",
          price: "10 Р",
          owner: "Светлана",
          article: "c4",
          available: true
          },
          {
          image: "5.webp",
          name: "Симон и Сима. Котята в добрые руки",
          city: "Москва",
          price: "Бесплатно",
          owner: "Светлана",
          article: "c5",
          available: true
          },
          {
          image: "6.webp",
          name: "Маленькие котята в добрые руки",
          city: "Москва",
          price: "10 Р",
          owner: "Светлана",
          article: "c6",
          available: true
          } 
       ]
      };
    },
  props: {},
  methods: {},
  };
</script>

<style>
  .v_catalog {
    background-color: #f4f7f9;
    display: flex;
    flex-wrap: wrap;
    margin: 0;
    padding: 0;
  }
</style>