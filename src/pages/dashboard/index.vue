<template>
  <div class="container">
    <div class="title">
      <img
        class="logo"
        src="https://img.yzcdn.cn/public_files/2017/12/18/fd78cf6bb5d12e2a119d0576bedfd230.png"
      />
      <div class="title-text">Vant Weapp</div>
    </div>
    <div class="desc">轻量、可靠的小程序 UI 组件库</div>
    <div
      v-for="(item,index) in list"
      :key="index"
    >
      <view class="mobile-nav">
        <view class="mobile-nav__title">{{ item.groupName }}</view>
        <van-cell-group>
          <van-cell
            v-for="(listItem,listIndex) in item.list"
            :key="listIndex"
            is-link
            :url="'/pages'+listItem.path+'/main'"
            :title="listItem.title"
            :border="listIndex!==item.list.length-1"
          />
        </van-cell-group>
      </view>
    </div>
  </div>
</template>

<script>
  import list from '../../config'

  export default {
    data () {
      return {
        list: list
      }
    },
    methods: {}
  }
</script>

<style lang="less">
  .container {
    padding: 45px 15px 0;
  }

  .title {
    margin: 0 0 15px;
    text-align: center;
    user-select: none;
  }

  .logo,
  .title-text {
    display: inline-block;
    vertical-align: middle;
  }

  .title-text {
    font-size: 32px;
    margin-left: 15px;
    font-weight: 400;
    font-family: "Dosis", "Source Sans Pro", "Helvetica Neue", Arial, sans-serif;
  }

  .logo {
    width: 36px;
    height: 36px;
  }

  .desc {
    font-size: 14px;
    color: #455a64;
    margin: 0 0 60px;
    text-align: center;
  }

  .mobile-nav {
    margin-bottom: 20px;
  }

  .mobile-nav__title {
    font-size: 16px;
    background-color: #fff;
    padding: 17px 15px;
  }

</style>
