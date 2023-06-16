<template>
  <div class="home">
    <h2>{{ counterData.title }}</h2>
    <div>
      <button @click="decreaseCounter(2)" class="btn">-2</button>
      <button @click="decreaseCounter(1)" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1)" class="btn">+</button>
      <button @click="increaseCounter(2)" class="btn">+2</button>
    </div>
  </div>
</template>


<!-- script setup -->
<script setup>
import { ref, reactive } from "vue";
const counter = ref(0);

const counterData = reactive({
  count: 0,
  title: "My counter"
})

const increaseCounter = (amount) => {
  console.log(amount)
  counterData.count = counterData.count + amount;
};
const decreaseCounter = (amount) => {
  counterData.count = counterData.count - amount;
};
</script>

<style>
.home {
  text-align: center;
  padding: 20px;
}

.btn,
.counter {
  font-size: 36px;
  margin: 10px;
}
</style>