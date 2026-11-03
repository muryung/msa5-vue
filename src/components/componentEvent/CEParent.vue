<script setup>
import { ref } from 'vue';
import CEChild from './CEChild.vue';

const cnt = ref(0);

const addCount = () => {
  cnt.value++;
}

const multiCount = (val) => {
  cnt.value *= val;
}
</script>

<template>
  <h2>CE Parent</h2>
  <CEChild @addCount="addCount" @multiCount="multiCount" />
  <p>카운트 : {{ cnt }}</p>
</template>

<style scoped>

</style>