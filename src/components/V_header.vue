<template>
  <div class="wrapper">
    <div>
      <vButton
        @click="showPopupChooseCity"
        btnTitle="Москва"
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

export default {
  name: "v_header",
  components: {
    vButton,
  },
  props: {},
  methods: {
    showPopupChooseCity() {
      this.$emit("showPopupChooseCity");
    },
    btnClick() {
      console.log("кнопка нажата");
    },
    closePopupChooseCity() {
      this.isPopupVisible = false;
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
