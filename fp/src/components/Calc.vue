<template>
  <div>
    <div>
      <input type="number" placeholder="op1" v-model.number="operand1" />
      <input placeholder="op2" v-model.number="operand2" type="number" />
      = {{ sum }}
    </div>
    <div>
      <button @click="sum = operand1 + operand2">+</button>
      <button @click="sum = operand1 - operand2">-</button>
      <button v-on:click="sum = operand1 * operand2">*</button>
      <button @click="div">/</button>
      <button @click="eventFv">Event</button>
      <button @click="power">^</button>
      <button @click="divFul">div</button>
    </div>
    result : {{ sum }}
    <!-- <div v-on:mouseover=""></div> -->
  </div>
</template>

<script>
export default {
  name: "Calc",
  data: () => ({
    operand1: 0,
    operand2: 0,
    sum: 0,
  }),
  methods: {
    eventFv() {
      console.log(arguments);
    },
    div() {
      this.sum = this.operand1 / this.operand2;
    },
    power() {
      this.sum = Math.pow(this.operand1, this.operand2);
    },
    divFul() {
      this.sum = Math.floor(this.operand1 / this.operand2);
    },
  },
};
</script>

<style>
</style>