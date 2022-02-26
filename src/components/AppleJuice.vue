<template>
    <div>
        <div style="color=red">{{ kevin }}</div>
        <div></div>
    </div>
</template>
<script >

import Vue from 'vue';

export default Vue.extend({
    name: 'AppleJuice',
    props: {
        kevin: String,
    },
});
</script>
<style>

</style>