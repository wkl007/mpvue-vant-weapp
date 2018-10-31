<template>
  <div class="container">
    <demo-block title="文字提示" padding>
      <van-button @click="showToast">文字提示</van-button>
    </demo-block>

    <demo-block title="加载提示" padding>
      <van-button @click="showLoadingToast">加载提示</van-button>
    </demo-block>

    <demo-block title="成功/失败提示" padding>
      <van-button @click="showSuccessToast" custom-class="demo-margin-right">成功提示</van-button>
      <van-button @click="showFailToast">失败提示</van-button>
    </demo-block>

    <demo-block title="高级用法" padding>
      <van-button @click="showCustomizedToast">高级用法</van-button>
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
      showToast () {
        Toast('我是提示文案，建议不超过十五字~')
      },
      showLoadingToast () {
        Toast.loading({mask: true, message: '加载中...'})
      },
      showSuccessToast () {
        Toast.success('成功文案')
      },
      showFailToast () {
        Toast.fail('失败提示')
      },
      showCustomizedToast (duration) {
        const text = second => `倒计时 ${second} 秒`
        const toast = Toast.loading({
          duration: 0,
          forbidClick: true,
          loadingType: 'spinner',
          message: text(3)
        })

        let second = 3
        const timer = setInterval(() => {
          second--
          if (second) {
            toast.setData({message: text(second)})
          } else {
            clearInterval(timer)
            Toast.clear()
          }
        }, 1000)
      }
    }
  }
</script>

<style>

</style>
