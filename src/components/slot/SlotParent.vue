<script setup>
import SlotChild from './SlotChild.vue';
</script>

<template>
  <h2>Slot Parent</h2>
  <SlotChild>부모에서 보낸 버튼</SlotChild>
  <SlotChild>전송</SlotChild>
  <SlotChild></SlotChild>
</template>

<style scoped>

</style>