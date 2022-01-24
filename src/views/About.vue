<template>
  <div>
    <input v-model="checked" type="checkbox"> 全选<br>
    <input :checked="checked" type="checkbox"> java <br>
    <input :checked="checked" type="checkbox"> c++ <br>
    <input :checked="checked" type="checkbox"> js <br>
    <div id="echarts"></div>
    <button @click="changeChartValue">改变高度</button>
  </div>
</template>

<script>
import * as echarts from 'echarts'

export default {
  name: 'About',
  data () {
    return {
      checked: false,
      myChart: {}
    }
  },
  mounted () {
    this.initEcharts()
  },
  methods: {
    initEcharts () {
      // initialize the echarts instance
      this.myChart = echarts.init(document.getElementById('echarts'))
      // Draw the chart
      this.myChart.setOption({
        title: {
          text: 'ECharts Getting Started Example',
          left: 'center'
        },
        tooltip: {},
        grid: [
          { left: '31%', top: '7%', width: '38%', height: '38%' },
          { left: '31%', bottom: '7%', width: '38%', height: '38%' }
        ],
        xAxis: [
          {
            type: 'category',
            gridIndex: 0,
            data: ['shirt', 'cardigan', 'chiffon', 'pants', 'heels', 'socks']
          },
          {
            type: 'category',
            gridIndex: 1,
            data: ['shirt', 'shirt', 'shirt', 'shirt', 'shirt', 'shirt']
          }
        ],
        yAxis: [
          { gridIndex: 0 },
          { gridIndex: 1 }
        ],
        series: [
          {
            name: 'sales',
            type: 'bar',
            xAxisIndex: 0,
            yAxisIndex: 0,
            data: [5, 20, 36, 10, 10, 20]
          },
          {
            name: 'sales',
            type: 'bar',
            xAxisIndex: 1,
            yAxisIndex: 1,
            data: [4, 4, 4, 4, 4, 4]
          },
          {
            name: 'sales',
            type: 'line',
            smooth: true,
            xAxisIndex: 0,
            yAxisIndex: 0,
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      })
    },
    changeChartValue () {
      this.myChart.setOption({
        series: [
          {
            name: 'sales',
            type: 'bar',
            xAxisIndex: 0,
            yAxisIndex: 0,
            data: [30, 10, 15, 20, 5, 50]
          },
          {
            name: 'sales',
            type: 'bar',
            xAxisIndex: 1,
            yAxisIndex: 1,
            data: [1, 2, 3, 4, 5, 6]
          },
          {
            name: 'sales',
            type: 'line',
            smooth: true,
            xAxisIndex: 0,
            yAxisIndex: 0,
            data: [30, 10, 15, 20, 5, 50]
          }
        ]
      })
    }
  }
}
</script>

<style scoped>
#echarts {
  width: 600px;
  height: 400px;
  margin: 0 auto;
  text-align: center;
}
</style>
