<template>
  <div>
    <demo-block title="选择完整时间">
      <van-datetime-picker
        type="datetime"
        :loading="loading"
        :value="currentDate1"
        :min-date="minDate"
        @change="onChange"
      />
    </demo-block>

    <demo-block title="选择日期（年月日）">
      <van-datetime-picker
        type="date"
        :value="currentDate2"
        :min-date="minDate"
        @change="onChange"
      />
    </demo-block>

    <demo-block title="选择日期（年月）">
      <van-datetime-picker
        type="year-month"
        :value="currentDate3"
        :min-date="minDate"
        @change="onChange"
      />
    </demo-block>

    <demo-block title="选择时间">
      <van-datetime-picker
        type="time"
        :value="currentDate4"
        :min-date="minDate"
        :min-hour="minHour"
        :max-hour="maxHour"
        @change="onChange"
      />
    </demo-block>
  </div>
</template>

<script>

  export default {
    data () {
      return {
        minHour: 10,
        maxHour: 20,
        minDate: new Date(2018, 0, 1).getTime(),
        maxDate: new Date(2019, 10, 1).getTime(),
        currentDate1: new Date(2018, 2, 1).getTime(),
        currentDate2: null,
        currentDate3: new Date(2018, 0, 1),
        currentDate4: '12:00',
        loading: false
      }
    },
    methods: {
      onChange ({mp}) {
        const {detail} = mp
        console.log(mp)
      }
    }
  }
</script>

<style lang="less">
  .container {
    width: auto;
    margin: 0 15px;
    padding: 20px 0;
    background-color: #fff;
  }

  .group {
    margin: 0 auto;
  }
</style>
