<script setup>

</script>

<script lang="ts">
export default {
  data() {
    return {
      count: 0,
      time: 15,
      type : 'A'
    }
  },
  mounted() {
    this.getCountdown();
  },
  methods: {
    //add money to the total money when user click
    add_money() {
      this.count += Math.random() + 1;
    },
    getCountdown() {
      let clock = window.setInterval(() => {
        this.content = this.totalTime + 's后重新发送';
        this.totalTime--;
        if (this.totalTime < 0) {
          this.type = 'C';
          window.clearInterval(clock);
        }
      }, 1000);
    }
  }
}
</script>

<template>
  <button v-if="type === 'A'" @click="type = 'B'" class="start-button">现在开始！</button>
  <h1 class="title" v-else-if="type === 'B'">现在你已获得{{ count.toFixed(2) }}元</h1>
  <h1 v-else> 结束！</h1>
  <h2 class="downclock">剩余时间：{{ time }}</h2>
  <button @click="add_money" class="main-button" v-if="type === 'B'"><img src="/red-packet.png"
      alt="The picture for an red packet" /></button>
</template>

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