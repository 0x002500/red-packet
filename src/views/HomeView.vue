<template>
  <button v-if="type === 'A'" @click="startGame" class="start-button">现在开始！</button>
  <h1 class="title" v-else-if="type === 'B'">现在你已获得{{ count.toFixed(2) }}元</h1>
  <h1 v-else> 结束！</h1>
  <h2 class="downclock">剩余时间：{{ time }}</h2>
  <button @click="addMoney" class="main-button" v-if="type === 'B'"><img src="/red-packet.png"
      alt="The picture for a red packet" /></button>
</template>

<script setup lang="ts">
import { ref } from 'vue';

let count = ref(0);
let time = ref(15);
let type = ref('A');

const addMoney = () => {
    count.value += Math.random() + 1;
};

let clockInterval: number;

const startGame = () => {
  type.value = 'B';
  const countdown = () => {
    time.value--;
    if (time.value < 0) {
      type.value = 'C';
      clearInterval(clockInterval);
    }
  };
  clockInterval = window.setInterval(countdown, 1000);
};
</script>

<style>
.main-button {
  position: absolute;
  left: 50%;
  transform: translate(-50%, 100%);
  background-image: url(/red-packet.png);
  background-size: cover;
}

.title {
  position: absolute;
  left: 50%;
  transform: translate(-50%, 0);
}

.downclock {
  position: absolute;
  right: 5%;
  transform: translate(-50%, 0);
}

.start-button {
  margin: auto;
  width: 50%;
  padding: 10px;
  transform: scale(1);
}
</style>  