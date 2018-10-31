<template>
  <div class="container">
    <demo-block title="消息提示" padding>
      <van-button
        plain
        type="primary"
        custom-class="demo-margin-right"
        @click="onClickAlert"
      >
        消息提示
      </van-button>
      <van-button
        plain
        type="primary"
        @click="onClickAlert2"
      >
        无标题提示
      </van-button>
    </demo-block>

    <demo-block title="消息确认" padding>
      <van-button
        plain
        type="primary"
        @click="onClickConfirm"
      >
        消息确认
      </van-button>
    </demo-block>

    <demo-block title="组件调用" padding>
      <van-button
        plain
        type="danger"
        @click="showCustomDialog"
      >
        组件调用
      </van-button>
      <van-dialog
        use-slot
        async-close
        :show="show"
        show-cancel-button
        @close="onClose"
        confirm-button-open-type="getUserInfo"
        @getuserinfo="getUserInfo"
      >
        <van-field
          :value="username"
          label="用户名"
          placeholder="请输入用户名"
        />
        <van-field
          :value="password"
          type="password"
          label="密码"
          :border="false"
          placeholder="请输入密码"
        />
      </van-dialog>
    </demo-block>

    <van-dialog id="van-dialog"/>
  </div>
</template>

<script>
  import Dialog from '../../../static/vant/dialog/dialog'

  const message = '有赞是一家零售科技公司，致力于成为商家服务领域里最被信任的引领者'

  export default {
    data () {
      return {
        show: false,
        username: '',
        password: ''
      }
    },
    methods: {
      showCustomDialog () {
        this.show = true
      },
      onClickAlert () {
        Dialog.alert({
          title: '标题',
          message
        })
      },
      getUserInfo ({mp}) {
        console.log(mp.detail)
      },
      onClickAlert2 () {
        Dialog.alert({
          message
        })
      },
      onClickConfirm () {
        Dialog.confirm({
          title: '标题',
          message
        }).then(() => {
          // on confirm
        }).catch(() => {
          // on cancel
        });
      },
      onClose ({mp}) {
        if (mp.detail === 'confirm') {
          setTimeout(() => {
            this.show = false
          }, 1000)
        } else {
          this.show = false
        }
      }
    }
  }
</script>

<style>

</style>
