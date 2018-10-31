<template>
  <div class="container">
    <demo-block title="基础用法">
      <van-slider custom-class="slider" value="50" @change="onChange" />
    </demo-block>

    <demo-block title="指定选择范围">
      <van-slider
        custom-class="slider"
        value="50"
        min="10"
        max="90"
        @change="onChange"
      />
    </demo-block>

    <demo-block title="禁用">
      <van-slider custom-class="slider" value="50" disabled />
    </demo-block>

    <demo-block title="指定步长">
      <van-slider
        custom-class="slider"
        value="50"
        step="10"
        bar-height="4px"
        @change="onChange"
      />
    </demo-block>

  </div>
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
          title: `当前值：${detail}`
        })
      }
    }
  }
</script>

<style lang="less">
  .slider {
    margin: 0 15px 30px;
  }
</style>
