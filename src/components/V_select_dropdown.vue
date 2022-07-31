<template>
  <div>
    <div class="title">
      <p>{{ title }}</p>
    </div>
    <div class="contaner">
      <div
        @click="isVisible = !isVisible"
        class="wrapper"
        :class="{ down: !isVisible, up: isVisible }"
      >
        <p :class="{ empty: !Boolean(selectedItem) }">
          {{ selectedItem?.name || placeholder }}
        </p>
        <div v-if="isVisible">
          <p
            v-for="(item, index) in items"
            :key="index"
            @click="(event) => itemSelector(event, item)"
            :class="{ item_selected: selectedItem?.value === item.value }"
          >
            {{ item.name }}
          </p>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "v_select_dropdown",
  emits: ["itemSelector"],
  props: {
    items: {
      type: Array,
      default() {
        return [];
      },
    },
    selectedItem: {
      type: Object,
    },
    placeholder: {
      type: String,
      default: "Выберите значение",
    },
    title: {
      type: String,
    },
  },
  data() {
    return {
      isVisible: false,
    };
  },
  methods: {
    itemSelector(event, item) {
      event.preventDefault();
      event.stopPropagation();
      this.$emit("itemSelector", item);
      this.isVisible = false;
    },
    vHideSelect(event) {
      const target = event.target;
      const isContains = this.$el.contains(target);
      if (!isContains) {
        this.isVisible = false;
      }
    },
  },
  mounted() {
    document.addEventListener("click", this.vHideSelect);
  },
  beforeUnmount() {
    document.removeEventListener("click", this.vHideSelect);
  },
};
</script>

<style lang="less" scoped>
.title {
  margin: 16px 25px;
}

.contaner {
  margin: 5px 25px;
  position: relative;

  > .wrapper {
    width: 100%;
    height: 60px;
    border: 1px;
    border-radius: 4px;
    background-color: #f4f7f9;
    border: 1px solid #a4ecce;
    cursor: pointer;

    &.wrapper::before {
      position: absolute;
      right: 15px;
      top: 25px;
      content: "";
      width: 10px;
      height: 10px;
      border-left: 2px solid #000;
      border-top: 2px solid #000;
      transition: transform linear 200ms;
    }

    &.down::before {
      transform: rotate(225deg);
    }

    &.up::before {
      transform: rotate(45deg);
    }

    > p {
      margin-left: 25px;
      margin-top: 20px;
      &.empty {
        color: green;
      }
    }

    > div {
      position: absolute;
      top: 50px;
      left: 0px;
      width: 100%;
      border: 1px;
      border-radius: 4px;
      background-color: #f4f7f9;
      box-sizing: border-box;
      z-index: 10;
      > p {
        font-size: 16px;
        &.item_selected {
          background-color: red;
        }
        &:hover {
          color: #0cb66f;
          text-decoration: underline;
        }
      }
    }
  }
}
</style>
