<template lang="">
    <div class="test">
        <ul class="aside_1212">
            <li><a href="#">會員管理</a></li>
            <li><a href="#">藝術陶管理</a></li>
            <li><a href="#">生活陶管理</a></li>
            <li><a href="#">課程管理</a></li>
            <li><a href="#">訂單管理</a></li>
        </ul>
    </div>
</template>
<script>
export default {
  name: 'TinaHung',
  data() {
    return {
      msg: "我是data中的數據",
    };
  },
};
</script>
<style lang="scss">
.test {
  background-color: rgb(58, 39, 39);
  width: 200px;
  .aside_1212 {
    padding-left: 0px;
    list-style: none;
    text-align: center;
  }
  .aside_1212 > li {
    padding: 20px 10px;
  }
  .aside_1212 > li > a {
    color: white;
    text-decoration: none;
  }
}
</style>