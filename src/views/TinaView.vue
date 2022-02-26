<template>
  <div class="tina">
    <div>
      i'm tina
      <AsideList/>
      <BananaQ/>
    </div>
  </div>
</template>
<script>
import Vue from "vue";
import AsideList from "../components/AsideList.vue"
import BananaQ from "../components/BananaQ.vue";
export default Vue.extend({
  name: 'HomeView',
  components: {
    AsideList,
    BananaQ,
  },
});

</script>
<style lang="scss">
  h1{
    color: red;
  }
</style>
