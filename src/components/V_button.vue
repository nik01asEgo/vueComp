<template>
  <div :class="choiceBtn" @click="click">
    <span>{{ btnTitle }}</span>
  </div>
</template>

<script>
export default {
  name: "vButton",
  data() {
    return {};
  },
  props: {
    btnTitle: {
      type: String,
      default: "Press",
    },
    submit: {
      type: Boolean,
      default: false,
    },
    entrance: {
      type: Boolean,
      default: false,
    },
  },
  methods: {
    click() {
      this.$emit("click");
    },
  },
  computed: {
    choiceBtn() {
      return {
        Btn_entrance: this.entrance,
        Btn_submit: this.submit,
      };
    },
  },
};
</script>

<style lang="less" scoped>
.Btn_entrance {
  display: flex;
  font-family: Montserrat, sans-serif;
  font-size: 19px;
  width: 150px;
  height: 55px;
  margin: 5px;
  background-color: rgb(255, 255, 255);
  border: 1px solid #ececec;
  border-radius: 4px;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transition-property: all;
  transition-timing-function: ease;
  transition-duration: 0.6s;
  transition-delay: 0s;
  &:hover {
    border: 1px solid #a4ecce;
    color: #0cb66f;
  }
}
.Btn_submit {
  display: flex;
  font-family: Montserrat, sans-serif;
  font-size: 19px;
  color: #ffffff;
  width: 250px;
  height: 55px;
  margin: 5px;
  background-color: #21ac50;
  border: 1px solid #ffffff;
  border-radius: 4px;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transition-property: all;
  transition-timing-function: ease;
  transition-duration: 0.6s;
  transition-delay: 0s;
  &:hover {
    background-color: #fff;
    border: 1px solid #a4ecce;
    color: #0cb66f;
  }
}
</style>
