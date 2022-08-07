<template>
  <div class="wrapper">
    <div>
      <vButton @click="btnClick" btnTitle="Войти" :entrance="true" :submit="false" />
      <vButton
        @click="btnClick"
        btnTitle="Подать объявление"
        :entrance="false"
        :submit="true"
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
  data() {
    return {
      title: "i am header",
    };
  },
  props: {},
  methods: {
    btnClick() {
      console.log("Кнопка нажата");
    },
  },
};
</script>

<style lang="less" scoped>
.wrapper {
  display: flex;
  width: 100%;
  height: 100px;
  justify-content: flex-end;

  background-color: #fff;
  > div {
    display: flex;
    align-items: center;
  }
}
</style>
