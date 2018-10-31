<template>
  <div class="container">
    <demo-block title="基础用法" padding>
      <van-stepper :value="value1"/>
    </demo-block>

    <demo-block title="禁用状态" padding>
      <van-stepper :value="value1" disabled/>
    </demo-block>

    <demo-block title="高级用法" padding>
      <van-stepper
        :value="value2"
        integer
        min="5"
        max="40"
        step="2"
      />
    </demo-block>

  </div>
</template>

<script>

  export default {
    data () {
      return {
        value1: 1,
        value2: 5
      }
    },
    methods: {}
  }
</script>

<style>

</style>
