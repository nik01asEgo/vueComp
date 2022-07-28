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
    <p>{{ selected }}</p>
    <vSelectAge
      :ages = 'ages'
      @select= 'ageSelect'
      >
    </vSelectAge>
  </div>
</template>

<script>
import vSelectAge from "../components/V_select_age.vue"
export default {
  name: "v_Navigation",
  components: {
    vSelectAge
  },
  data() {
    return {
      ages: [
        {name: 'Любой', value: 1},
        {name: 'Собаки', value: 2},
        {name: ' Новорожденные (1-2 недели)', value: 3},
        {name: ' Щенки (до 1 года)', value: 4},
        {name: ' Взрослые (1-6 лет)', value: 5},
        {name: ' Пожилые (старше 6 лет)', value: 6},
        {name: 'Кошки', value: 7},
        {name: ' Котенок (до 1 года)', value: 8},
        {name: ' Взрослые (1-7 лет)', value: 9},
        {name: ' Пожилые (Старше 7 лет)', value: 10},
      ],
      selected: ''
    };
  },
  methods: {
    ageSelect (age) {
      this.selected = age.value
    }
  },
};
</script>

<style >
.v_Navigation {
  border: 1px;
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
  border: 1px;
  border-radius: 4px;
  background-color: #f4f7f9;
}
.v_Navigation_City_Contaner {
  margin: 5px 25px;
  box-sizing: border-box;
}

</style>