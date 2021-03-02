<template>
  <div class="component_sum">
    <h3 class="title">Sum two number</h3>

    <form @submit.prevent="onSubmit">
      <label for="firstnumber">First number</label>
      <input
        v-model.number="firstNumber"
        type="number"
        id="firstnumber"
        name="firstnumber"
        placeholder="Entrer first number.."
        step="0.1"
      />

      <label for="firstnumber">Second number</label>
      <input
        v-model.number="secondNumber"
        type="number"
        id="secondnumber"
        name="secondnumber"
        placeholder="Entrer second number.."
        step="0.1"
      />

      <input type="submit" value="Sum" />
    </form>

    <div class="sum" v-if="firstNumber && secondNumber && sum">
      {{ firstNumber + " + " + secondNumber + " = " + sum.toFixed(2) }}
    </div>
  </div>
</template>

<script>
export default {
  name: "Sum",
  data() {
    return {
      firstNumber: null,
      secondNumber: null,
      sum: null,
    };
  },
  methods: {
    onSubmit() {
      this.sum = this.firstNumber + this.secondNumber;
    },
  },
  watch: {
    firstNumber() {
      this.sum = this.firstNumber + this.secondNumber;
    },
    secondNumber() {
      this.sum = this.firstNumber + this.secondNumber;
    },
  },
};
</script>
<style>
input[type="number"],
select {
  width: 100%;
  padding: 12px 20px;
  margin: 2px 0;
  display: inline-block;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
}

input[type="submit"] {
  width: 100%;
  background-color: #3c53d8;
  color: white;
  padding: 14px 20px;
  margin: 2px 0;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: #05285c;
}

.component_sum {
  width: 50%;
  margin: auto;
  border-radius: 5px;
  background-color: #f2f2f2;
  padding: 20px;
}
.title {
  text-align: center;
}
div.sum {
  width: 100%;
  padding: 12px 20px;
  margin: 2px 0;
  text-align: center;
  border-radius: 4px;
}
</style>
