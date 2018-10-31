<template>
  <div class="container">
    <demo-block title="基础用法">
      <van-tabbar :active="active" custom-class="tabbar" @change="onChange">
        <van-tabbar-item icon="shop">标签</van-tabbar-item>
        <van-tabbar-item icon="chat" dot>标签</van-tabbar-item>
        <van-tabbar-item icon="records" info="5">标签</van-tabbar-item>
        <van-tabbar-item icon="gold-coin" info="20">标签</van-tabbar-item>
      </van-tabbar>
    </demo-block>
    <demo-block title="自定义图标">
      <van-tabbar :active="active2" custom-class="tabbar" @change="onChange">
        <van-tabbar-item>
          <span>自定义</span>
          <image slot="icon" :src="icon.normal " class="icon" mode="aspectFit"/>
          <image slot="icon-active" :src="icon.active" mode="aspectFit"/>
        </van-tabbar-item>
        <van-tabbar-item icon="chat">标签</van-tabbar-item>
        <van-tabbar-item icon="records">标签</van-tabbar-item>
      </van-tabbar>
    </demo-block>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        active: 0,
        active2: 0,
        icon: {
          normal:
            'https://img.yzcdn.cn/public_files/2017/10/13/c547715be149dd3faa817e4a948b40c4.png',
          active:
            'https://img.yzcdn.cn/public_files/2017/10/13/793c77793db8641c4c325b7f25bf130d.png'
        }
      }
    },
    methods: {
      onChange ({mp}) {
        const {detail} = mp
        console.log(detail)
      }
    }
  }
</script>

<style lang="less">
  .tabbar {
    position: relative !important;
  }

</style>
