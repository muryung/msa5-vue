<script setup>
import { ref } from 'vue';

const items = ref([
  {
    id: 1,
    kinds: '중식',
    food: '짜장면'
  },
  {
    id: 2,
    kinds: '한식',
    food: '비빔밥'
  },
  {
    id: 3,
    kinds: '일식',
    food: '돈까스'
  },
]);
</script>

<template>
  <h2>List Rendering</h2>

  <div class="container">
    <div v-for="item in items" :key="item.id" class="card">
      <p>{{ item.kinds }}</p>
      <p>{{ item.food }}</p>
    </div>
  </div>
</template>

<style>

</style>