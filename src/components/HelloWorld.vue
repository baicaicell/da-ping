<template>
  <div id="myChart" ref="myChart" style="width: 100%;height:480px;"></div>
</template>

<script>

export default {
  name: 'HelloWorld',
  data() {
    return {
      option: {
        xAxis: {
          type: 'category',
          data: ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun']
        },
        yAxis: {
          type: 'value'
        },
        series: [
          {
            data: [120, 200, 150, 80, 70, 110, 130],
            type: 'bar'
          }
        ]
      }
    }
  },
  methods: {
    getChart() {
      // 在步骤2的方法1中 通过 this.$echarts.init方法初始化echarts实例并使用 setOption 方法注册图表配置项和数据
      let myChart = this.$echarts.init(document.getElementById("myChart"));
      myChart.setOption(this.option);
    }
  },
  mounted() {
    this.getChart();
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
