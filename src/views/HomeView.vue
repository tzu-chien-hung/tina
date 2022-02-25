<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg= "Welcome to Your Vue.js + TypeScript App"/>
    <AppleJuice kevin = "11" />
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from '../components/HelloWorld.vue';
import AppleJuice from '../components/AppleJuice.vue';

// @ is an alias to /src

export default Vue.extend({
  name: 'HomeView',
  components: {
    HelloWorld,
    AppleJuice,
  },
});
</script>
