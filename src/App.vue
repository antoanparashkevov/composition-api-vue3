<template>
  <section class='container'>
   <user-data :first-name='firstName' :last-name='lastName' :user-age='user.userAge'></user-data>
    <button @click='setNewAge'>Click me</button>
    <div>
      <input type='text' placeholder='First Name' v-model='firstName'>
      <input type='text' placeholder='Last Name' ref='lastNameInput'>
    </div>
    <button @click='setLastName'>Set Last Name</button>
  </section>
</template>

<script>
import { computed, reactive, ref,watch } from 'vue';
import userData from '@/components/userData';
export default {
  components:{
    userData
  },
  setup() {
    // const uName = ref('Antoan')
    // const uAge = ref(21)
    const firstName = ref('');
    const lastName = ref('');
    const lastNameInput = ref(null)
    const user = reactive({
      // userName:'Antoan',
      userAge: 21
    });

    const uName = computed(function() {
      return firstName.value + " " +  lastName.value;
    });

    watch([uName,user],function(oldValues,newValues){
      console.log('Old value for name: ' + oldValues[0])
      console.log('New value for name: ' + newValues[0])
      console.log('Old value for age: ' + oldValues[1].userAge)
      console.log('New value for age: ' + newValues[1].userAge)
    })

    function setAge() {
      user.userAge = 22;
    }

    function setLastName(){
      lastName.value = lastNameInput.value.value
    }

    // function setFirstName(event) {
    //   firstName.value = event.target.value;
    // }
    //
    // function setLastName(event) {
    //   lastName.value = event.target.value;
    //
    // }

    // setTimeout(function(){
    //   user.userName = 'Test'
    //   user.userAge = 22
    // },2000)

    return {
      uName,
      user: user,
      setNewAge: setAge,
      firstName,
      setLastName,
      lastNameInput,
      lastName
    };
  }
  // data() {
  //   return {
  //     userName: 'Maximilian',
  //   };
  // },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}

.container {
  margin: 3rem auto;
  max-width: 30rem;
  border-radius: 12px;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.26);
  padding: 1rem;
  text-align: center;
}
</style>
