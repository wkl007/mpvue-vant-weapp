<template>
  <div class="container">
    <demo-block title="基础用法">
      <van-tree-select
        :items="items"
        :main-active-index="mainActiveIndex"
        :active-id="activeId"
        @clickItem="onClickItem"
        @clickNav="onClickNav"
      ></van-tree-select>
    </demo-block>
  </div>
</template>

<script>
  import config from './config'

  export default {
    data () {
      return {
        items: [
          {
            // 导航名称
            text: '所有城市',
            // 该导航下所有的可选项
            children: [...config.pro1, ...config.pro2]
          }, {
            // 导航名称
            text: config.pro1Name,
            // 该导航下所有的可选项
            children: config.pro1
          }, {
            text: config.pro2Name,
            children: config.pro2
          }
        ],
        mainActiveIndex: 0,
        activeId: 1002
      }
    },
    methods: {
      onClickNav ({mp}) {
        this.mainActiveIndex = mp.detail.index || 0
      },
      onClickItem ({mp}) {
        this.activeId = mp.detail.id
      }
    }
  }
</script>

<style>

</style>
