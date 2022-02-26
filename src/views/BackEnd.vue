<template lang="">
    <div class="backend backend_scss">
        <TinaHung/>
        <MainList title="會員管理" tina="2"/>
        <AppleJuice kevin = "apple juice"/>
    </div>
</template>
<script>
import Vue from "vue";
import AppleJuice from "../components/AppleJuice.vue";
import TinaHung from "../components/TinaHung.vue";
import MainList from "../components/MainList.vue";

export default Vue.extend({
  name: "BackEnd",
  components: {
    TinaHung,
    AppleJuice,
    MainList,
  },
});
</script>
<style lang="scss">
    .backend_scss{
        display: flex;
    }
</style>