<script setup>
import { ref } from 'vue';
import Child from './Child.vue';

const user = ref({
  id: 1,
  name: '홍길동',
  age: 20
});
const str = ref('전달 문자열');

</script>

<template>
  <h2>Parent</h2>
  <Child :item="user" :str="str"/>
</template>

<style>

</style>