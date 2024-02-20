<script setup>

</script>

<script lang="ts">
//check the random type
const isInteger = (obj: unknown) => {
  return typeof obj === 'number' && obj % 1 === 0;
};
//change the type
const keeptwo = (num: number) => {
  return Number(num.toString().match(/^\d+(?:\.\d{0,2})?/));
};

export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    onclick() {
      if (isInteger(Math.random()) == false) this.count += keeptwo(Math.random() + 1)
      else this.count += Math.random();
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