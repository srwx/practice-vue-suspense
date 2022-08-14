<template>
  <input type="number" v-model="num1" @keyup="addNumbers" />
  +
  <input type="number" v-model="num2" @keyup="addNumbers" />
  =
  <span class="result">{{ result }}</span>
</template>

<script>
import { ref } from "vue";

export default {
  name: "CalculatorComponent",

  setup() {
    let num1 = ref(0);
    let num2 = ref(0);
    let result = ref(0);

    function addNumbers() {
      result.value = num1.value + num2.value;
    }

    return {
      num1,
      num2,
      result,
      addNumbers,
    };
  },
};
</script>
