<template>
  <div class="container">
    <demo-block title="基本用法">
      <van-search
        :value="value"
        placeholder="请输入搜索关键词"
        @change="onChange"
        @search="onSearch"
      />
    </demo-block>

    <demo-block title="监听对应事件">
      <van-search
        :value="value"
        show-action
        placeholder="请输入搜索关键词"
        @change="onChange"
        @search="onSearch"
        @cancel="onCancel"
      />
    </demo-block>

    <demo-block title="自定义行动按钮">
      <van-search
        :value="value"
        placeholder="请输入搜索关键词"
        use-action-slot
        @change="onChange"
        @search="onSearch"
      >
        <view slot="action" @click="onSearch">搜索</view>
      </van-search>
    </demo-block>

  </div>
</template>

<script>

  export default {
    data () {
      return {
        value: ''
      }
    },
    methods: {
      onChange ({mp}) {
        const {detail} = mp
        this.value = detail
      },
      onSearch ({mp}) {
        if (this.value) {
          wx.showToast({
            title: '搜索：' + this.value,
            icon: 'none'
          })
        }
      },
      onCancel () {
        wx.showToast({
          title: '取消',
          icon: 'none'
        })
      }
    }
  }
</script>

<style>

</style>
