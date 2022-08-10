<template>
  <div class="v_Navigation">
    <div class="v_Navigation_span_container">
      <span class="v_Navigation_H1">Найти </span>
      <span class="v_Navigation_Clear_Filters" @click="clearSelectedItem"
        >Сбросить фильтры</span
      >
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
    <vSelectDropdown
      :items="adTypes"
      :selectedItem="adTypeSelected"
      placeholder="Выберите тип"
      title="Тип объявления"
      @itemSelector="(item) => (adTypeSelected = item)"
    />
    <vSelectDropdown
      :items="genders"
      :selectedItem="genderSelected"
      placeholder="Выберите пол"
      title="Пол питомца"
      @itemSelector="(item) => (genderSelected = item)"
    />
    <vSelectDropdown
      :items="colors"
      :selectedItem="colorSelected"
      placeholder="Выберите цвет"
      title="Цвет питомца"
      @itemSelector="(item) => (colorSelected = item)"
    />
    <div class="btn_wrapper">
      <div class="btn_search"><p>Поиск</p></div>
    </div>
  </div>
</template>

<script>
import vSelectDropdown from "@/components/V_select_dropdown.vue";
import { breeds, ages, adTypes, genders, colors } from "@/static_store";

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
      adTypes,
      adTypeSelected: undefined,
      genders,
      genderSelected: undefined,
      colors,
      colorSelected: undefined,
    };
  },
  methods: {
    clearSelectedItem() {
      this.ageSelected = undefined;
      this.breedSelected = undefined;
      this.adTypeSelected = undefined;
      this.genderSelected = undefined;
      this.colorSelected = undefined;
    },
  },
};
</script>

<style lang="less" scoped>
.v_Navigation {
  border: 1px;
  text-align: left;
  background-color: rgb(255, 255, 255);

  > .btn_wrapper {
    margin: 30px 25px;
    box-sizing: border-box;
    position: relative;

    > .btn_search {
      width: 100%;
      height: 80px;
      box-sizing: border-box;
      border-radius: 4px;
      background-color: #212529;
      cursor: pointer;
      display: flex;

      &:hover {
        background-color: #0cb66f;
      }

      > p {
        margin: auto;
        color: #f4f7f9;
        font-size: 20px;
      }
    }
  }
  .v_Navigation_span_container {
    padding: 25px 20px 25px 20px;

    .v_Navigation_H1 {
      font-size: 24px;
      margin-right: 40px;
      text-align: left;
    }
    .v_Navigation_Clear_Filters {
      font-size: 17px;
      text-align: right;
      cursor: pointer;
    }
  }
  .v_Navigation_City_Contaner {
    margin: 5px 25px;
    box-sizing: border-box;

    .v_Navigation_Input_City {
      width: 100%;
      height: 60px;
      border: 1px;
      border-radius: 4px;
      background-color: #f4f7f9;
    }
  }
}
</style>
