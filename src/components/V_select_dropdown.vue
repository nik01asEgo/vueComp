<template>
  <div>
    <div class="title">
      <p>{{ title }}</p>
    </div>
    <div class="contaner">
      <div
        @click="isVisible = !isVisible"
        class="wrapper"
        :class="{ down: !isVisible, up: isVisible, full: Boolean(selectedItem) }"
      >
        <p :class="{ empty: !Boolean(selectedItem) }">
          {{ selectedItem?.name || placeholder }}
        </p>
        <div
          v-if="isVisible"
          :class="{ selected: Boolean(selectedItem), unSelected: !Boolean(selectedItem) }"
        >
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
    // clearSelectedItem: {
    //   type: Object,
    // },
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
    // clearSelectedItem: function () {
    //   this.selectedItem.value = "";
    // },
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
  box-sizing: border-box;
  margin: 5px 25px;
  position: relative;

  > .wrapper {
    width: 100%;
    min-height: 60px;
    border: 1px;
    border-radius: 4px;
    box-sizing: border-box;
    background-color: #f4f7f9;
    border: 1px solid #f4f7f9;
    cursor: pointer;

    &.full {
      border: 1px solid #a4ecce;
      &.down {
        background-color: #e7f0ec;
      }
    }
    &.wrapper::before {
      position: absolute;
      right: 15px;
      top: 25px;
      content: "";
      width: 5px;
      height: 5px;
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
      margin-right: 25px;

      &.empty {
        opacity: 0.5;
      }
    }

    > div {
      position: absolute;
      top: 55px;
      left: 0px;
      width: 100%;
      max-height: 300px;
      border: 1px;
      border-radius: 4px;
      background-color: #f4f7f9;
      box-sizing: border-box;
      z-index: 10;
      overflow: auto;

      &.unSelected {
        border-left: 1px solid #f4f7f9;
        border-bottom: 1px solid #f4f7f9;
        border-right: 1px solid #f4f7f9;
      }
      &.selected {
        border-left: 1px solid #a4ecce;
        border-bottom: 1px solid #a4ecce;
        border-right: 1px solid #a4ecce;
      }
      > p {
        font-size: 15px;
        margin-left: 25px;
        &:hover {
          color: #0cb66f;
          text-decoration: underline;
        }
      }
    }
  }
}
</style>
