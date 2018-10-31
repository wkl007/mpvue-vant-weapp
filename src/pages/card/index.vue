<template>
  <div class="container">
    <demo-block title="基础用法">
      <van-card
        num="2"
        price="2.00"
        desc="描述信息"
        title="商品标题"
        :thumb="imageURL"
      />
    </demo-block>

    <demo-block title="高级用法">
      <van-card
        num="2"
        tag="标签"
        price="2.00"
        origin-price="3.00"
        desc="描述信息"
        title="商品标题"
        :thumb="imageURL"
      >
        <view slot="tags">
          <van-tag plain type="danger">满减</van-tag>
        </view>
        <view slot="footer">
          <van-button size="mini" custom-class="button">按钮</van-button>
          <van-button size="mini">按钮</van-button>
        </view>
      </van-card>
    </demo-block>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        imageURL: '//img.yzcdn.cn/upload_files/2017/07/02/af5b9f44deaeb68000d7e4a711160c53.jpg'
      }
    },
    methods: {}
  }
</script>

<style class="less">
  .container {
    height: 100vh;
    background-color: #fff;
  }

  .button {
    margin-right: 5px;
  }

</style>
