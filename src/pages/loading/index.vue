<template>
  <div class="container">
    <demo-block title="Circular" padding>
      <van-loading custom-class="loading"/>
      <van-loading custom-class="loading shadow" color="#fff"/>
    </demo-block>

    <demo-block title="Spinner" padding>
      <van-loading custom-class="loading" type="spinner"/>
      <van-loading custom-class="loading shadow" type="spinner" color="#fff"/>
    </demo-block>
  </div>
</template>

<script>

  export default {
    data () {
      return {}
    },
    methods: {}
  }
</script>

<style lang="less">
  .loading {
    margin-right: 20px;
  }

  .shadow {
    padding: 10px;
    border-radius: 3px;
    background-color: rgba(0, 0, 0, .5);
  }
</style>
