<template>
  <div class="container">
    <demo-block title="基本用法">
      <van-radio-group :value="radio1" data-key="radio1" @change="onChange" custom-class="demo-radio-group">
        <van-radio name="1" custom-class="demo-radio">单选框 1</van-radio>
        <van-radio name="2" custom-class="demo-radio">单选框 2</van-radio>
      </van-radio-group>
    </demo-block>
    <demo-block title="禁用状态">
      <van-radio-group :value="radio2" data-key="radio2" @change="onChange" disabled custom-class="demo-radio-group">
        <van-radio name="1" custom-class="demo-radio">单选框 1</van-radio>
        <van-radio name="2" custom-class="demo-radio">单选框 2</van-radio>
      </van-radio-group>
    </demo-block>
    <demo-block title="与 Cell 组件一起使用">
      <van-radio-group :value="radio3">
        <van-cell-group>
          <van-cell title="单选框 1" clickable data-value="1" @click="onClick">
            <van-radio name="1"/>
          </van-cell>
          <van-cell title="单选框 2" clickable data-value="2" @click="onClick">
            <van-radio name="2"/>
          </van-cell>
        </van-cell-group>
      </van-radio-group>
    </demo-block>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        radio1: '1',
        radio2: '2',
        radio3: '1'
      }
    },
    methods: {
      onChange ({mp}) {
        const {detail, currentTarget: {dataset: {key}}} = mp
        this[key] = detail
      },
      onClick ({mp}) {
        const {currentTarget: {dataset: {value}}} = mp
        this.radio3 = value
      }
    }
  }
</script>

<style lang="less">
  .demo-radio-group {
    padding: 0 17px;
  }

  .demo-radio {
    margin-bottom: 10px;
  }
</style>
