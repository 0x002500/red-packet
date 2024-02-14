<script setup>

</script>

<script>
export default {
  data() {
    return {
      count: 0
    }
  }
}
</script>

<template>
  <p class="title">现在你以获得{{ count }}元</p>
  <button @click="count++" class="main-button"><img src="/red-packet.png" alt="The picture for an red packet" /></button>
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