<template>
  <div class="v_Navigation">
    <div class="v_Navigation_span_container">
      <span class="v_Navigation_H1">Найти </span>
      <span class="v_Navigation_Clear_Filters">Сбросить фильтры</span>
    </div>
    <div class="v_Navigation_City_Contaner">
      <p class="v_Navigation_City">Город/Область</p>
      <input
        class="v_Navigation_Input_City"
        type="text"
        placeholder="Название города или области"
      />
    </div>
    <vSelectDropdown
      :items="ages"
      :selectedItem="ageSelected"
      placeholder="Выберите Тип/Возраст питомца"
      title="Тип питомца/Возраст"
      @itemSelector="(item) => (ageSelected = item)"
    />
    <vSelectDropdown
      :items="breeds"
      :selectedItem="breedSelected"
      placeholder="Выберите породу питомца"
      title="Порода/Вид"
      @itemSelector="(item) => (breedSelected = item)"
    />
  </div>
</template>

<script>
import vSelectDropdown from "@/components/V_select_dropdown.vue";

import { breeds, ages } from "@/static_store";

export default {
  name: "v_Navigation",
  components: {
    vSelectDropdown,
  },
  data() {
    return {
      ages,
      ageSelected: undefined,
      breeds,
      breedSelected: undefined,
    };
  },
  methods: {},
};
</script>

<style>
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
