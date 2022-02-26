<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg= "Welcome to Your Vue.js + TypeScript App"/>
    <AppleJuice kevin = "11" />
    <TinaHung/>
  
  </div>
</template>

<script lang="ts">
import Vue from 'vue';
import HelloWorld from '../components/HelloWorld.vue';
import AppleJuice from '../components/AppleJuice.vue';
import TinaHung from '../components/TinaHung.vue';
// @ is an alias to /src

export default Vue.extend({
  name: 'HomeView',
  components: {
    HelloWorld,
    AppleJuice,
    TinaHung,
  },
});
</script>
<style lang="scss">
.aside_1212 > li:first-child{
        background-color:rgba(255, 255, 255, 0.199);
  }
</style>
