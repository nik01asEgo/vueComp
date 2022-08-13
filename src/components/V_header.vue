<template>
  <div class="wrapper">
    <Teleport v-if="isModalShowed" to="#v-portal-modal">
      <vPopup
        :items="cities"
        @close="isModalShowed = false"
        @change="onCityChange"
      />
    </Teleport>
    <div>
      <vButton
        @click="isModalShowed = true"
        :btnTitle="currentCity?.name || 'Выберите город'"
        :entrance="false"
        :submit="false"
        :chooseCity="true"
        prependIcon="location_on"
        appendIcon="expand_more"
      />
      <vButton
        @click="btnClick"
        btnTitle="Войти"
        :entrance="true"
        :submit="false"
        prependIcon="person"
        appendIcon=""
      />
      <vButton
        @click="btnClick"
        btnTitle="Подать объявление"
        :entrance="false"
        :submit="true"
        prependIcon=""
        appendIcon=""
      />
    </div>
  </div>
</template>

<script>
import vButton from "@/components/V_button.vue";
import vPopup from "@/components/V_popup.vue";
import { cities } from "@/static_store";

export default {
  name: "v_header",
  components: {
    vButton,
    vPopup,
  },
  data() {
    return {
      cities,
      currentCity: undefined,
      isModalShowed: false,
    };
  },
  props: {},
  methods: {
    btnClick() {
      console.log("кнопка нажата");
    },
    onCityChange(city) {
      this.currentCity = city;
      this.isModalShowed = false;
    },
  },
};
</script>

<style lang="less" scoped>
.wrapper {
  box-sizing: border-box;
  display: flex;
  width: 100%;
  justify-content: flex-end;
  background-color: #fff;
  > div {
    display: flex;
    align-items: center;
    margin-left: 180px;
    margin-right: 180px;
  }
}
</style>
