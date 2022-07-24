<template>
  <div class="v_catalog_item_contaner">
    <div class= "v_catalog_item">
      <div class="v_catalog_item_image_contaner">
        <a href="http://google.com">
          <img class="v_catalog_item_image" 
          :src="require ('../assets/images/' + item_data.image)" 
          alt= "webp">
        </a>
      </div>        
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
  
<style>
.v_catalog_item_contaner {
  width: 33%;
  padding: 10px;
  box-sizing: border-box;
}
.v_catalog_item {
  display: block;
  width: 100%;
  height: 500px;
  background-color: rgb(255, 255, 255);
  border-radius: 4px;
  border: 1px;
}
@media screen and (max-width: 900px) {
  .v_catalog_item {
    width: 50%;
} 
  }
.v_catalog_item_image_contaner {
  width: 100%;
  height: 250px;    
}
.v_catalog_item_image {
  width: 100%;
  height: 100%;
  object-fit: cover;
  border-radius: 4px;    
}
.v_catalog_item_name {
  text-decoration: none;
  color: rgb(12, 12, 12);
  font-family: Montserrat,sans-serif;
  font-size: 19px;
  font-weight: 500;
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