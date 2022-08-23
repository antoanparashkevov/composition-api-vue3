<template>
  <h2>{{ userName }}</h2>
  <p>{{ userAge }}</p>
</template>

<script>
export default {
  name: 'userData',
  props:['userName','userAge']
};
</script>

<style scoped>

</style>
