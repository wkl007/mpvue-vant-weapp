<template>
  <div class="container">
    <demo-block title="基础用法">
      <van-goods-action custom-class="goods-action">
        <van-goods-action-icon
          icon="chat"
          text="客服"
          open-type="contact"
        />
        <van-goods-action-icon
          icon="cart"
          text="购物车"
          @click="onClickIcon"
        />
        <van-goods-action-button
          text="加入购物车"
          type="warning"
          @click="onClickButton"
        />
        <van-goods-action-button
          text="立即购买"
          @click="onClickButton"
        />
      </van-goods-action>
    </demo-block>

    <demo-block title="图标提示">
      <van-goods-action custom-class="goods-action">
        <van-goods-action-icon icon="chat" text="客服" />
        <van-goods-action-icon icon="cart" text="购物车" info="5" />
        <van-goods-action-icon icon="shop" text="店铺" />
        <van-goods-action-button text="加入购物车" type="warning" />
        <van-goods-action-button text="立即购买" />
      </van-goods-action>
    </demo-block>

    <van-toast id="van-toast" />
  </div>
</template>

<script>
  import Toast from '../../../static/vant/toast/toast'

  export default {
    data () {
      return {}
    },
    methods: {
      onClickIcon () {
        Toast('点击图标')
      },
      onClickButton () {
        Toast('点击按钮')
      }
    }
  }
</script>

<style lang="less">
  .goods-action {
    position: relative !important;
  }
</style>
