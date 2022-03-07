<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
  </div>
  <pass-input></pass-input>
</template>


<script>
import PassInput from '@/components/pass.vue';


export default {

  name: 'HomeView',
  components: {
    PassInput,
  }

}
</script>
