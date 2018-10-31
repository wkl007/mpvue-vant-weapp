<template>
  <demo-block title="基础用法">
    <div class="container">
      <van-badge-group @change="onChange" custom-class="group">
        <van-badge title="标签名称"/>
        <van-badge title="标签名称" info="8"/>
        <van-badge title="标签名称" info="99"/>
        <van-badge title="标签名称" info="199"/>
      </van-badge-group>
    </div>
  </demo-block>
</template>

<script>

  export default {
    data () {
      return {}
    },
    methods: {
      onChange ({mp}) {
        const {detail} = mp
        wx.showToast({
          icon: 'none',
          title: `切换至第${detail}项`
        })
      }
    }
  }
</script>

<style lang="less">
  .container {
    width: auto;
    margin: 0 15px;
    padding: 20px 0;
    background-color: #fff;
  }

  .group {
    margin: 0 auto;
  }
</style>
