<template>
  <div :class="choiceBtn" @click="click">
    <i class="material-icons" v-if="prependIcon">{{ prependIcon }}</i>
    <span>{{ btnTitle }}</span>
    <i class="material-icons" v-if="appendIcon">{{ appendIcon }}</i>
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
      default: "",
    },
    submit: {
      type: Boolean,
      default: false,
    },
    entrance: {
      type: Boolean,
      default: false,
    },
    chooseCity: {
      type: Boolean,
      default: false,
    },
    close: {
      type: Boolean,
      default: false,
    },
    fix: {
      type: Boolean,
      default: false,
    },
    appendIcon: {
      type: String,
      default: "",
    },
    prependIcon: {
      type: String,
      default: "",
    },
  },
  methods: {
    click() {
      // event.preventDefault();
      // event.stopPropagation();
      this.$emit("click");
    },
  },
  computed: {
    choiceBtn() {
      return {
        Btn_entrance: this.entrance,
        Btn_submit: this.submit,
        Btn_choose_city: this.chooseCity,
        Btn_close: this.close,
        Btn_fix: this.fix,
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
  user-select: none;
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
  user-select: none;
  &:hover {
    background-color: #fff;
    border: 1px solid #a4ecce;
    color: #0cb66f;
  }
}
.Btn_choose_city {
  display: flex;
  font-family: Montserrat, sans-serif;
  font-size: 19px;
  max-width: 250px;
  height: 55px;
  margin: 5px;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  user-select: none;
}
.Btn_close {
  display: flex;
  width: 50px;
  height: 50px;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  user-select: none;
}
&.material-icons {
  font-size: 22px;
  margin: 4px;
}
</style>
