<script setup>

</script>

<script lang="ts">
export default {
  data() {
    return {
      count: 0,
      time: 15
    }
  },
  methods: {
    //add money to the total money when user click
    onclick() {
      this.count += Math.random() + 1;
    }
  }
}
</script>

<template>
    <h1 class="title">现在你已获得{{ count.toFixed(2) }}元</h1>
    <h2 class="downclock">剩余时间：{{ time }}</h2>
  <button @click="onclick" class="main-button"><img src="/red-packet.png" alt="The picture for an red packet" /></button>
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
</style>