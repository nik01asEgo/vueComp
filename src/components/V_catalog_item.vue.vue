<template>
  <div class= "v_catalog_item">
    <a href="http://google.com">
      <img class="v_catalog_item_image" 
      :src="require ('../assets/images/' + item_data.image)" 
      alt= "webp">
    </a>        
    <a class="v_catalog_item_name" href="http://google.com">
        <p >{{ item_data.name }}</p>
    </a>
    
    <a class="v_catalog_item_city" href="http://google.com">
        <p >{{ item_data.city }}</p>
    </a>

        <p class="v_catalog_item_price">{{ item_data.price }}</p>

    <a class="v_catalog_item_owner" href="http://google.com">
        <p >{{ item_data.owner }}</p>
    </a>
  </div>
</template>

<script>
export default {
  name: "V_catalog_item",
  created() {},
  data() {
    return {};
  },
  props: {
    item_data: {
      type: Object,
      default () {
        return {}
      }
    }
  },
  methods: {},
};
</script>
  
<style scoped>
  .v_catalog_item {
    display: block;
    border: 1px solid;
    position:relative;
    text-align: center;
    max-width: 33%;
    height: 500 px;
    background-color: rgb(255, 255, 255);
  }
  .v_catalog_item_image {
    
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
  margin: 20px;
  object-fit: cover;
  display: block;
  margin: auto;
    
  }
.v_catalog_item_name {

  text-decoration: none;
  color: rgb(12, 12, 12);
  font-family: Montserrat,sans-serif;
  font-size: 19px;
  font-weight: 500;
  text-align: left;
  margin-left: 15 px;

}
.v_catalog_item_city {
  
  text-decoration: none;
  color: #777;
  font-family: Montserrat,sans-serif;
  font-size: 16px;
  font-weight: 500;
  text-align: left;
  
}
.v_catalog_item_owner {

  text-decoration: none;
  color: #777;
  font-family: Montserrat,sans-serif;
  font-size: 15px;
  font-weight: 500;
  text-align: left;

}
.v_catalog_item_price {

  text-decoration: none;
  color: rgb(12, 12, 12);
  font-family: Montserrat,sans-serif;
  font-size: 19px;
  font-weight: 500;
  text-align: left;
}

</style>