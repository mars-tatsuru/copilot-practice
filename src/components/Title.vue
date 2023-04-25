<!-- eslint-disable vue/multi-word-component-names -->
<script setup lang="ts">

defineProps({
  title: String,
});

</script>

<template>
  <h2>{{title}}</h2>
</template>


<style scoped lang="scss">
h2 {
  font-size: 2rem;
  font-weight: 700;
  margin: 0;
  padding: 0;
  color: #000;
}
</style>
