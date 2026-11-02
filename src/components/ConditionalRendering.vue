<script setup>
import { ref } from 'vue';

const num = ref(0);
const flg = ref(true);
</script>

<template>
  <input type="number" v-model="num">
  <p v-if="num === 0">0 입니다.</p>
  <p v-else-if="num % 2 === 0">짝수 입니다.</p>
  <p v-else>홀수 입니다.</p>
  <hr>
  <button :class="{ 'btn-toggle': flg === false }" @click="flg = !flg">토글</button>
  <p v-if="flg">v-if</p>
  <p v-show="flg">v-show</p>
</template>

<style>
.btn-toggle {
  background-color: powderblue;
}
</style>