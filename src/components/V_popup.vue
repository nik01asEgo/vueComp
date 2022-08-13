<template>
  <div class="v_popup_contaner">
    <div class="v_popup">
      <vButton
        class="close_btn"
        :close="true"
        prependIcon="close"
        @click="$emit('close')"
      >
      </vButton>
      <div class="v_wrapper">
        <span>Выберите город</span>
        <div class="input_wrapper"></div>
        <div class="cities_wrapper">
          <p
            v-for="(item, index) in items"
            :key="index"
            @click="$emit('change', item)"
          >
            {{ item.name }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import vButton from "@/components/V_button.vue";
export default {
  name: "v_popup",
  emits: ["change", "close"],
  components: {
    vButton,
  },
  props: {
    items: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  data() {
    return {};
  },
  methods: {
    btnClick() {
      console.log("кнопка нажата");
    },
    onKeyDown(event) {
      if (event.key === "Escape") {
        this.$emit("close");
      }
    },
  },
  mounted() {
    window.addEventListener("keydown", this.onKeyDown);
  },
  beforeUnmount() {
    window.removeEventListener("keydown", this.onKeyDown);
  },
};
</script>

<style lang="less">
.v_popup_contaner {
  display: flex;
  justify-content: center;
  align-items: center;
  position: fixed;
  right: 0;
  left: 0;
  top: 0;
  bottom: 0;
  background-color: rgba(64, 64, 64, 0.4);
  z-index: 15;

  .v_popup {
    display: flex;
    flex-direction: column;
    position: relative;
    width: 1125px;
    height: 600px;
    z-index: 20;
    background-color: #ffffff;
    border-radius: 5px;

    .close_btn {
      align-self: flex-end;
    }
    .v_wrapper {
      display: flex;
      flex-direction: column;
      width: 100%;
      margin-left: 50px;
      margin-right: 50px;
      > span {
        margin-top: 50px;
        text-align: left;
        font-size: 30px;
        font-family: Montserrat, sans-serif;
        font-weight: 500;
      }
      .input_wrapper {
        height: 60px;
      }
      .cities_wrapper {
        display: grid;
        grid-template-columns: 1fr 1fr 1fr;
        grid-gap: 0px;

        > p {
          margin: 0;
          margin-top: 10px;
          text-align: left;
          font-size: 19px;
          cursor: pointer;
          user-select: none;
          &:hover {
            text-decoration: underline;
            color: #0cb66f;
            transition-property: all;
            transition-timing-function: ease;
            transition-duration: 0.3s;
            transition-delay: 0s;
          }
        }
      }
    }
  }
}
</style>
