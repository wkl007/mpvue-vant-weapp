<template>
  <div class="container">
    <demo-block title="基础用法">
      <van-rate
        custom-class="van-rate"
        :data-key="value1"
        :value="value1"
      />
    </demo-block>

    <demo-block title="自定义图标">
      <van-rate
        custom-class="van-rate"
        icon="like"
        void-icon="like-o"
        :data-key="value2"
        :value="value2"
      />
    </demo-block>

    <demo-block title="自定义样式">
      <van-rate
        custom-class="van-rate"
        :data-key="value3"
        :value="value3"
        :size="25"
        :count="6"
        color="#2ba"
        void-color="#ceefe8"
        @change="onChange"
      />
    </demo-block>

    <demo-block title="禁用状态">
      <van-rate
        custom-class="van-rate"
        :data-key="value4"
        :value="value4"
        disabled
      />
    </demo-block>
  </div>
</template>

<script>
  export default {
    data () {
      return {
        value1: 3,
        value2: 3,
        value3: 4,
        value4: 2
      }
    },
    methods: {
      onChange ({mp}) {
        const {detail} = mp
        this.value3 = detail
      }
    }
  }
</script>

<style lang="less">
  .van-rate {
    margin-left: 15px;
  }
</style>
