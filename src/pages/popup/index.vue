<template>
  <div class="container">
    <demo-block title="基础用法" padding>
      <van-button @click="togglePopup">弹出 Popup</van-button>
      <van-popup
        :show="show.middle"
        custom-class="center"
        @close="togglePopup"
      >
        内容
      </van-popup>
    </demo-block>
    <demo-block title="弹出位置" padding>
      <van-button @click="toggleBottomPopup" custom-class="demo-margin-right">底部弹出</van-button>

      <van-popup
        :show="show.bottom"
        position="bottom"
        custom-class="bottom"
        @close="toggleBottomPopup"
      >
        内容
      </van-popup>

      <van-button @click="toggleTopPopup" custom-class="demo-margin-right">顶部弹出</van-button>
      <van-popup
        :show="show.top"
        position="top"
        :overlay="false"
        custom-class="top"
        @close="toggleTopPopup"
      >
        内容
      </van-popup>

      <van-button @click="toggleRightPopup">右侧弹出</van-button>
      <van-popup
        :show="show.right"
        position="right"
        custom-class="right"
        @close="toggleRightPopup"
      >
        <van-button @click="toggleRightPopup" custom-class="demo-margin-right">关闭弹层</van-button>

        <van-button @click="toggleRightPopup2">右侧弹出</van-button>
        <van-popup
          :show="show.right2"
          position="right"
          custom-class="right"
          @close="toggleRightPopup2"
        >
          <van-button @click="toggleRightPopup2">关闭弹层</van-button>
        </van-popup>
      </van-popup>
    </demo-block>

  </div>
</template>

<script>

  export default {
    data () {
      return {
        show: {
          middle: false,
          top: false,
          bottom: false,
          right: false,
          right2: false
        }
      }
    },
    methods: {
      toggle (type) {
        this.show[type] = !this.show[type]
      },
      togglePopup () {
        this.toggle('middle')
      },
      toggleRightPopup () {
        this.toggle('right')
      },
      toggleRightPopup2 () {
        this.toggle('right2')
      },
      toggleBottomPopup () {
        this.toggle('bottom')
      },
      toggleTopPopup () {
        this.toggle('top')
        setTimeout(() => {
          this.toggle('top')
        }, 2000)
      }
    }
  }
</script>

<style lang="less">
  :host {
    font-size: 16px;
  }

  .center {
    width: 60%;
    padding: 20px;
    text-align: center;
    box-sizing: border-box;
  }

  .top {
    color: #fff;
    width: 100%;
    padding: 20px;
    border-radius: 0;
    line-height: 20px;
    background-color: rgba(0, 0, 0, 0.8) !important;
  }

  .bottom {
    width: 100%;
    padding: 20px;
    line-height: 100px;
    background-color: #fff;
  }

  .right {
    width: 100%;
    height: 100%;
    padding: 20px;
  }

</style>
