<template>
  <div class="container">
    <demo-block title="基础用法">
      <van-swipe-cell :right-width="65" :left-width="65">
        <view slot="left" class="van-swipe-cell__left">选择</view>
        <van-cell-group>
          <van-cell title="单元格" value="内容"/>
        </van-cell-group>
        <view slot="right" class="van-swipe-cell__right">删除</view>
      </van-swipe-cell>
    </demo-block>

    <demo-block title="异步关闭">
      <van-swipe-cell id="swipe-cell" :right-width="65" :left-width="65" async-close @close="onClose">
        <view slot="left" class="van-swipe-cell__left">选择</view>
        <van-cell-group>
          <van-cell title="单元格" value="内容"/>
        </van-cell-group>
        <view slot="right" class="van-swipe-cell__right">删除</view>
      </van-swipe-cell>
    </demo-block>

    <van-dialog id="van-dialog"/>
  </div>
</template>

<script>
  import Dialog from '../../../static/vant/dialog/dialog'

  export default {
    data () {
      return {}
    },
    methods: {
      onClose ({mp}) {
        console.log(mp.detail)
        const {position, instance} = mp.detail
        switch (position) {
          case 'left':
          case 'cell':
            instance.close()
            break
          case 'right':
            Dialog.confirm({
              message: '确定删除吗？'
            }).then(() => {
              instance.close()
            }).catch(err => {})
            break
        }
      }
    }
  }
</script>

<style lang="less">
  .demo-swipe-cell {
    user-select: none;
  }

  .van-swipe-cell__left,
  .van-swipe-cell__right {
    display: inline-block;
    width: 65px;
    height: 44px;
    font-size: 15px;
    line-height: 44px;
    color: #fff;
    text-align: center;
    background-color: #f44;
  }

</style>
