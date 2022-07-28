<template>
  <div>
    <div class="v_title">
    <p>Тип питомца/Возраст</p>
    </div>
      <div class="v_select_age_contaner">
        <div class="v_select_age">
          <p       
                @click="v_age_visible=!v_age_visible"
          >
            select
          </p>
        <div 
              class="v_age"
              v-if="v_age_visible"
              @click="vAgeSelect"
        >
          <p 
              v-for= "age in ages"
              :key= "age.value"
          >
            {{ age.name }}  
          </p>
        </div>
      </div>
    </div>
  </div>  
</template>

<script>
export default {
  name: "v_select_age",
  props: {
    ages: {
      type: Array,
      default () {
        return []
      }
    }
  },
  data () {
    return {
      v_age_visible: false
    }
  },
  methods: {
    vAgeSelect (age) {
      this.$emit (Event, 'select', age)
    }
  },
};
</script>

<style>
.v_select_age_contaner {
  margin: 5px 25px;
  position: relative;
}
.v_select_age {
  width: 100%;
  height: 60px;
  border: 1px;
  border-radius: 4px;
  background-color: #f4f7f9;
  border: 1px solid #a4ecce;
  
}
.v_select_age p {
  cursor: pointer;
  margin-left: 25px;
}
.v_title {
  margin:16px 25px;
}
.v_age {
  position:absolute;
  top: 50px;
  left: 0px;
  width: 100%;
  border: 1px;
  border-radius: 4px;
  background-color: #f4f7f9;
  box-sizing: border-box;
}
.v_age p:hover {
  color: #0cb66f;
  text-decoration: underline;
}
</style>