<template>
  <div>
    <div class="v_title">
      <p>Порода/Вид</p>
    </div>
    <div class="v_select_breed_contaner">
    <div @click="v_breed_visible = !v_breed_visible" class="v_select_breed">
      <p>{{ breedSelected }}</p>
      <div class="v_breed" v-if="v_breed_visible">
        <p
          v-for="(breed, index) in breeds"
          :key="index"
          @click="v_breed_select(breed)"
          :class="v_breed_selected"
        >
          {{ breed.name }}
        </p>
      </div>
    </div>
  </div>
</div>
</template>

<script>
export default {
  name: "v_select_breed",
  props: {
    breeds: {
      type: Array,
      default() {
        return [];
      },
    },
    breedSelected: {
      type: String,
      default: "",
    },
  },
  data() {
    return {
      v_breed_visible: false,
    };
  },
  methods: {
    v_breed_select(breed) {
      this.$emit("breedSelect", breed);
      this.v_breed_visible = "false";
    },
    vHideSelect() {
      this.v_breed_visible = "false";
    },
  },
  // mounted() {
  //   document.addEventListener("click", this.vHideSelect);
  // },
  // beforeUnmount() {
  //   document.removeEventListener("click", this.vHideSelect);
  // },
};
</script>

<style>
/* .arrow {
  transform: rotate(225deg);
  width: 10px;
  height: 10px;
  border-left: 2px solid #000;
  border-top: 2px solid #000;
} */
.v_select_breed_contaner {
  margin: 5px 25px;
  position: relative;
}
.v_select_breed {
  width: 100%;
  height: 60px;
  border: 1px;
  border-radius: 4px;
  background-color: #f4f7f9;
  border: 1px solid #a4ecce;
  cursor: pointer;
}
.v_select_breed p {
  margin-left: 25px;
  margin-top: 20px;
}
.v_title {
  margin: 16px 25px;
}
.v_breed {
  position: absolute;
  top: 50px;
  left: 0px;
  width: 100%;
  border: 1px;
  border-radius: 4px;
  background-color: #f4f7f9;
  box-sizing: border-box;
}
.v_breed p:hover {
  color: #0cb66f;
  text-decoration: underline;
}
</style>
