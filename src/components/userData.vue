<template>
  <h2>{{ userName }}</h2>
  <p>{{ userAge }}</p>
</template>

<script>
import {computed} from 'vue';

export default {
  props:['firstName','lastName','userAge'],
  setup(props){
    const userName = computed(function(){
      return props.firstName + " " + props.lastName;
    })
    return {userName}
  }
};
</script>

<style scoped>

</style>
