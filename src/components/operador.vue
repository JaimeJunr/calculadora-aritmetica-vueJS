<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
const props = defineProps(['option'])
</script>

<template>
  <select @change="props.option">
    <option value="+">+</option>
    <option value="-">-</option>
    <option value="*">x</option>
    <option value="/">/</option>
  </select>
</template>

<style scoped>
select {
  background-color: #5f6368;
  color: white;
  font-size: 24px;
  border: none;
  font-weight: bold;
}
</style>
