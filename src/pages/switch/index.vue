<template>
  <div class="container">
    <demo-block title="基础用法" padding>
      <van-switch
        :checked="checked"
        @change="onChange"
      />
    </demo-block>

    <demo-block title="禁用状态" padding>
      <van-switch
        :checked="checked"
        disabled
        @change="onChange"
      />
    </demo-block>

    <demo-block title="加载状态" padding>
      <van-switch
        :checked="checked"
        loading
        @change="onChange"
      />
    </demo-block>

    <demo-block title="高级用法" padding>
      <van-switch
        :checked="checked2"
        size="36px"
        @change="onChange2"
      />
    </demo-block>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        checked: true,
        checked2: true
      }
    },
    methods: {
      onChange ({mp}) {
        const {detail} = mp
        this.checked = detail
      },
      onChange2 ({mp}) {
        const {detail} = mp
        wx.showModal({
          title: '提示',
          content: '是否切换开关？',
          success: res => {
            if (res.confirm) {
              this.checked2 = detail
            }
          }
        })
      }
    }
  }
</script>

<style>

</style>
