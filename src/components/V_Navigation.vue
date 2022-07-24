<template>
  <div class="v_Navigation">
    <div class="v_Navigation_span_container">
      <span class="v_Navigation_H1">Найти </span>
      <span class="v_Navigation_Clear_Filters">Сбросить фильтры</span>
    </div>
    <div class="v_Navigation_City_Contaner">
      <p class="v_Navigation_City">Город/Область</p>
      <input class="v_Navigation_Input_City" type="text" placeholder="Название города или области">
    </div>
  </div>
</template>

<script>
export default {
  name: "v_Navigation",
  
  created() {},
  
  data() {
    return {
      
    };
  },
  props: {},
  methods: {},
};
</script>

<style >
.v_Navigation {
  border: 1px solid;
  display: block;
  text-align: left;
  background-color: rgb(255, 255, 255);
}
.v_Navigation_span_container {
 padding: 25px 20px 25px 20px;
}
.v_Navigation_H1 {
  font-size: 24px;
  margin-right: 40px;
  }
.v_Navigation_Clear_Filters {
  font-size: 17px;
}
.v_Navigation_Input_City {
  width: 100%;
  height: 60px;
  border-radius: 4px;

}
.v_Navigation_City_Contaner {
  margin: 5px 25px;
  box-sizing: border-box;
}

</style>