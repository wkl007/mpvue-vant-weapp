<template>
  <div class="container">
    <demo-block title="图标列表">
      <van-col
        custom-class="col"
        span="8"
        v-for="(item,index) in icons"
        :key="index"
      >
        <van-icon custom-class="icon" :name="item" size="32px"/>
        <view class="text">{{ item }}</view>
      </van-col>
    </demo-block>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        icons: [
          'close',
          'upgrade',
          'add-o',
          'passed',
          'chat',
          'question',
          'clock',
          'gold-coin',
          'play',
          'pause',
          'stop',
          'more-o',
          'info-o',
          'share',
          'aim',
          'like-o',
          'logistics',
          'edit',
          'exchange',
          'location',
          'cart',
          'shop',
          'gift',
          'contact',
          'wap-home',
          'points',
          'discount',
          'point-gift',
          'after-sale',
          'edit-data',
          'delete',
          'records',
          'completed',
          'certificate',
          'tosend',
          'sign',
          'photo',
          'idcard',
          'home',
          'free-postage',
          'cash-back-record',
          'points-mall',
          'exchange-record',
          'pending-payment',
          'pending-orders',
          'pending-deliver',
          'pending-evaluate',
          'password-view',
          'password-not-view',
          'check',
          'arrow',
          'arrow-left',
          'search',
          'success',
          'fail',
          'add',
          'checked',
          'warn',
          'clear',
          'underway',
          'more',
          'like',
          'photograph',
          'qr-invalid',
          'qr',
          'add2',
          'wechat',
          'alipay',
          'wap-nav',
          'ecard-pay',
          'balance-pay',
          'peer-pay',
          'credit-pay',
          'debit-pay',
          'other-pay',
          'shopping-cart',
          'browsing-history',
          'goods-collect',
          'shop-collect',
          'receive-gift',
          'send-gift',
          'setting',
          'coupon',
          'gift-card-pay',
          'cash-on-deliver',
          'phone',
          'description',
          'card',
          'value-card',
          'gift-card',
          'hot',
          'new',
          'new-arrival',
          'hot-sale',
          'cart-o'
        ]
      }
    },
    methods: {}
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
</style>
