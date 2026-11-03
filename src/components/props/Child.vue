<script setup>

const { item, str } = defineProps({
  'item': Object,
  'str': String
});
</script>

<template>
  <h2>Child</h2>
  <p>{{ item.name }}</p>
</template>

<style>

</style>