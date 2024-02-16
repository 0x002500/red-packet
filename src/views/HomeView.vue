<script setup>

</script>

<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    onclick() {
      var now_num = (Math.random() * 2).toFixed(2);
      this.count += now_num;
    }
  }
}
</script>

<template>
  <h1 class="title">现在你已获得{{ count }}元</h1>
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
</style>