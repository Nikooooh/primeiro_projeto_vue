<template>
  <div class="calculator">
    <input type="number" v-model="num1" @input="calculate" />
    <select v-model="operator" @change="calculate">
      <option value="add">+</option>
      <option value="subtract">-</option>
      <option value="multiply">*</option>
      <option value="divide">/</option>
    </select>
    <input type="number" v-model="num2" @input="calculate" />
    <p class="result">Result: {{ result }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: "add",
      result: 0,
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case "add":
          this.result = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case "subtract":
          this.result = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case "multiply":
          this.result = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case "divide":
          this.result = parseFloat(this.num1) / parseFloat(this.num2);
          break;
        default:
          this.result = 0;
      }
    },
  },
};
</script>

<style>
.calculator {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-top: 50px;
}

input,
select {
  margin-bottom: 10px;
  padding: 5px;
  font-size: 16px;
}

.result {
  font-size: 18px;
  font-weight: bold;
}
</style>
