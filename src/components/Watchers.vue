<script setup>
import { ref, watch } from 'vue';

const test = ref('');
const testErrorMsg = ref('O');
const testColor = ref('');

// Watchers
watch(test, (val) => {
  const pattern = /^[a-zA-Z]+$/;

  if (val === '') {
    testErrorMsg.value = '';
  } else if (pattern.test(val)) {
    testErrorMsg.value = 'O';
    testColor.value = 'color: green;';
  } else {
    testErrorMsg.value = 'X';
    testColor.value = 'color: red;';
  }
});
</script>

<template>
  <h2>Watchers: 감시자</h2>
  <!-- v-model: 양방향 바인딩 -->
  <input type="text" v-model="test">
  <p :style="testColor">{{ testErrorMsg }}</p>
</template>

<style>

</style>