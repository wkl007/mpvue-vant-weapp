<template>
  <div class="container">
    <demo-block padding title="基础用法">
      <van-button @click="showNotify">显示消息通知</van-button>
    </demo-block>

    <demo-block padding title="自定义配置">
      <van-button @click="showNotify2">显示自定义消息通知</van-button>
    </demo-block>

    <van-notify id="van-notify" />
    <van-notify id="custom-selector" />
  </div>
</template>

<script>
  import Notify from '../../../static/vant/notify/notify'

  export default {
    data () {
      return {}
    },
    methods: {
      showNotify () {
        Notify('通知内容')
      },
      showNotify2 () {
        Notify({
          duration: 1000,
          text: '通知内容',
          selector: '#custom-selector',
          backgroundColor: '#38f'
        })
      }
    }
  }
</script>

<style>

</style>
