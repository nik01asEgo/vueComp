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
      <div class="v_text_contaner">
        <a class="v_catalog_item_name" href="http://google.com">
            <p >{{ item_data.name }}</p>
        </a>
        <a class="v_catalog_item_city" href="http://google.com">
            <p >{{ item_data.city }}</p>
        </a>

        <p class="v_catalog_item_price">{{ item_data.price }}</p>
        <hr class="v_line">
      </div>    
      <div class="v_owner_contaner">
        <a class="v_catalog_item_owner" href="http://google.com">
        <p >{{ item_data.owner }}</p>
        </a>
      </div>
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
.v_line {
  color: rgb(196, 196, 196);
  opacity: 50%;
}
.v_text_contaner {
  margin: 25px;
}
.v_owner_contaner {
  margin: 25px;
}
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
@media screen and (max-width: 860px) {
  .v_catalog_item_contaner {
    width: 50%;
} 
  }
@media screen and (min-width: 550px) and (max-width: 600px) {
  .v_catalog_item {
    width: 100%;
    height: 280px;
    display: grid;
    grid-template-areas:
    'image text'
    'image text'
    'image text'
    'image owner'
    'image owner';
  grid-gap: 10px;
  grid-template-columns: 220px 1fr;
  grid-template-rows: 1fr 1fr 1fr 1fr 1fr; 
  }
  .v_catalog_item_contaner {
    width: 100%;
    }
  .v_catalog_item_image_contaner {
    grid-area: image;   
    }
  .v_text_contaner {
    text-align: left;
    grid-area: text;
  }
  .v_owner_contaner {
    grid-area: owner;
  }
}
@media screen and (max-width: 550px) {
  .v_catalog_item {
    width: 100%;
    height: 250px;
    display: grid;
    grid-template-areas:
    'image text'
    'image text'
    'owner owner';
  grid-gap: 15px;
  grid-template-columns: 5fr 6fr;
  grid-template-rows: 1fr 1fr 1fr; 
  }
  .v_catalog_item_contaner {
    width: 100%;
    }
  .v_catalog_item_image_contaner {
    grid-area: image;  
    margin: 0; 
    height: 100%;
    }
  .v_text_contaner {
    text-align: left;
    grid-area: text;
    margin: 0;
  }
  .v_owner_contaner {
    grid-area: owner;
    margin: 0;
  }
  .v_line {
    display: none;
  }
}
</style>