<template>
  <div class="container">
    <demo-block title="基础用法">
      <van-area
        :loading="loading"
        :area-list="areaList"
      />
    </demo-block>

    <demo-block title="选中省市县">
      <van-area
        :value="value"
        :loading="loading"
        :area-list="areaList"
      />
    </demo-block>

    <demo-block title="配置显示列">
      <van-area
        title="标题"
        :columns-num="2"
        :loading="loading"
        :area-list="areaList"
        @change="onChange"
        @confirm="onChange"
      />
    </demo-block>

  </div>
</template>

<script>
  import area from './area'

  export default {
    data () {
      return {
        areaList: area,
        loading: false,
        value: 610103
      }
    },
    methods: {

      onChange ({mp}) {
        console.log(mp)
      }
    }
  }
</script>

<style>

</style>
