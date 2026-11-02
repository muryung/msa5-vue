<script setup>
import { ref } from 'vue';

const count = ref(0);
const bgColor = ref('');
const email = ref('');

const toggleBgColor = () => {
  if (bgColor.value === '') {
    bgColor.value = 'bg-red';
  } else {
    bgColor.value = '';
  }
}
</script>

<template>
  <div @click="count++" class="btn-cnt" :class="bgColor">Count is {{ count }}</div>
  <button @click="count = 0">Count Reset</button>
  <button @click="count > 0 ? count-- : 0">Count down</button>
  <button @click="bgColor = 'bg-red'">Red</button>
  <button @click="bgColor = ''">cadetblue</button>
  <button @click="toggleBgColor()">Toggle</button>
  <br><br>
  <input type="text" name="email" id="email" v-model="email">
</template>

<style>
  .btn-cnt {
    width: 100px;
    height: 100px;
    background-color: #5f9ea0;
  }
  
  /* 아래꺼 위로 올리면 작동 안 함 */
  .bg-red {
    background-color: #ff0000;
  }
</style>