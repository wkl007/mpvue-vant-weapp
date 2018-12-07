<template>
  <van-tabs
    :active="active"
    @change="onSwitch"
  >
    <van-tab title="基础图标" custom-class="demo-tab-pane">
      <van-col
        v-for="(item,index) in basic"
        :key="index"
        custom-class="col"
        span="8"
      >
        <van-icon
          :name="item"
          size="32px"
          custom-class="icon"
        />
        <view class="text">{{ item }}</view>
      </van-col>
    </van-tab>
    <van-tab title="线框风格" custom-class="demo-tab-pane">
      <van-col
        v-for="(item,index) in outline"
        :key="index"
        custom-class="col"
        span="8"
      >
        <van-icon
          :name="item"
          size="32px"
          custom-class="icon"
        />
        <view class="text">{{ item }}</view>
      </van-col>
    </van-tab>
    <van-tab title="实底风格" custom-class="demo-tab-pane">
      <van-col
        v-for="(item,index) in filled"
        :key="index"
        custom-class="col"
        span="8"
      >
        <van-icon
          :name="item"
          size="32px"
          custom-class="icon"
        />
        <view class="text">{{ item }}</view>
      </van-col>
    </van-tab>
  </van-tabs>
</template>

<script>
  import config from './config'

  const basic = config.basic.map(item => item.css)
  const outline = config.outline.map(item => item.css)
  const filled = config.filled.map(item => item.css)

  export default {
    data () {
      return {
        basic,
        outline,
        filled,
        active: 0
      }
    },
    methods: {
      onSwitch ({mp}) {
        const {index} = mp.detail
        this.active = index
      }
    }
  }
</script>

<style lang="less">
  .col {
    text-align: center;
    height: 100px;
    float: none;
    display: inline-block;
    vertical-align: middle;
  }

  .icon {
    display: block;
    margin: 15px 0;
    color: rgba(69, 90, 100, .8);
  }

  .text {
    font-size: 14px;
  }

  .demo-tab-pane {
    padding-top: 10px;
  }

</style>
