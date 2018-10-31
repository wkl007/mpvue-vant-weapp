<template>
  <div class="container">
    <demo-block title="基础用法">
      <van-tabs :active="1" @change="onChange">
        <van-tab
          v-for="(item,index) in [1,2,3,4]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </demo-block>
    <demo-block title="横向滚动">
      <van-tabs>
        <van-tab
          v-for="(item,index) in [1,2,3,4,5,6]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </demo-block>
    <demo-block title="禁用标签">
      <van-tabs @disabled="onClickDisabled">
        <van-tab
          v-for="(item,index) in [1,2,3]"
          :key="index"
          :title="'标签' + item"
          :disabled="index === 1"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </demo-block>

    <demo-block title="样式风格">
      <van-tabs type="card">
        <van-tab
          v-for="(item,index) in [1,2,3]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content-2">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </demo-block>

    <demo-block title="点击事件">
      <van-tabs @iclick="onClick">
        <van-tab
          v-for="(item,index) in [1,2]"
          :key="index"
          :title="'标签' + item"
        >
          <view class="content">
            {{ '内容' + item }}
          </view>
        </van-tab>
      </van-tabs>
    </demo-block>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        tabs: [1, 2, 3, 4],
        tabsMore: [1, 2, 3, 4, 5, 6, 7, 8]
      }
    },
    methods: {
      onClickDisabled ({mp}) {
        const {detail} = mp
        console.log(detail)
        wx.showToast({
          title: `标签 ${detail.index + 1} 已被禁用`,
          icon: 'none'
        })
      },
      onChange ({mp}) {
        const {detail} = mp
        console.log(detail)
        wx.showToast({
          title: `切换到标签 ${detail.index + 1}`,
          icon: 'none'
        })
      },
      onClick ({mp}) {
        const {detail} = mp
        console.log(detail)
        wx.showToast({
          title: `点击标签 ${detail.index + 1}`,
          icon: 'none'
        })
      }
    }
  }
</script>

<style lang="less">
  .content {
    padding: 20px;
    background-color: #fff;
  }

  .content-2 {
    padding: 20px;
  }
</style>
