<!-- eslint-disable vue/multi-word-component-names -->
<script setup>
const props = defineProps(['result'])
</script>

<template>
  <div>
    <h1>{{ props.result }}</h1>
  </div>
</template>

<style scoped>
div {
  border: 2px rgb(255, 255, 255, 0.5) solid;
  border-radius: 10px;
  width: 50%;
  max-width: 484px;
  display: flex;
  justify-content: right;
}

h1 {
  padding-right: 8px;
  color: white;
    Verdana, sans-serif;
  font-size: 32px;
}
</style>
