<template>
  <h2>{{ userName }}</h2>
  <p>{{ userAge }}</p>
</template>

<script>
export default {
  name: 'userData',
  props:['firstName','lastName','userAge'],
  computed:{
    userName(){
      return this.firstName + " " + this.lastName
    }
  }
};
</script>

<style scoped>

</style>
