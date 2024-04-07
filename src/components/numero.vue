<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
const props = defineProps(['change'])
</script>

<template>
  <input type="number" @input="props.change" />
</template>

<style scoped>
input {
  background-color: #5f6368;
  border: none;
  height: 40px;
  font-size: 32px;
  color: white;
  padding-left: 8px;
}

input[type='number']:focus {
  border: lightblue 5px solod;
  text-decoration: none;
}
</style>
