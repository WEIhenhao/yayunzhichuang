/**历届亚运会参赛运动员人数变化图**/
<template>
  <div class="com-container">
    <div class="com-chart" ref="mn_ref"></div>
  </div>
</template>

<script>
export default {
  data () {
    return {
      chartInstance: null
    }
  },
  destroyed () {
    window.removeEventListener('resize', this.updataChart)
  },
  mounted () {
    this.initChart()
    this.updataChart()
    window.addEventListener('resize', this.updataChart)
    this.updataChart()
  },
  methods: {
    initChart () {
      this.chartInstance = this.$echarts.init(this.$refs.mn_ref)
    },
    updataChart () {
      // const textfontsize = this.$refs.mn_ref.offsetWidth / 100 * 3.6
      const option = {
        backgroundColor: '#F5F5F5',
        title: {
          text: '历届亚运会参赛运动员人数变化图',
          subtext: '数据来源：百度百科',
          itemGap: 5,
          x: 'center',
          y: '1%',
          textStyle: {
            fontFamily: 'sans-serif',
            fontSize: 21,
            fontWeight: 'normal'
          },
          subtextStyle: {
            color: '#646464',
            fontFamily: 'sans-serif',
            fontSize: 15,
            fontWeight: 'normal'
          }
        },
        tooltip: {
          trigger: 'axis',
          axisPointer: {
            type: 'line'
          }
        },
        xAxis: {
          type: 'category',
          axisLine: {
            show: false
          },
          axisTick: {
            show: false
          },
          axisLabel: {
            fontSize: 15
          },
          boundaryGap: true,
          data: ['第一届', '第二届', '第三届', '第四届', '第五届', '第六届', '第七届', '第八届', '第九届', '第十届', '第十一届', '第十二届', '第十三届', '第十四届', '第十五届', '第十六届', '第十七届', '第十八届', '第十九届'
          ]
        },
        yAxis: [{
          type: 'value',
          axisLine: {
            show: false,
            lineStyle: {
              color: '#000000'
            }
          },
          axisLabel: {
            fontSize: 15
          },
          min: 200,
          splitNumber: 6
        }],
        dataZoom: [{
          type: 'slider',
          filterMode: 'filter',
          show: true,
          height: 15,
          left: '11%',
          right: '10%',
          xAxisIndex: [
            0
          ],
          bottom: '1%',
          start: 0,
          end: 50,
          handleStyle: {
            color: '#40bcf9',
            borderColor: '#1fb2fb'
          },
          backgroundColor: '#e2f3ff',
          dataBackground: {
            lineStyle: {
              color: '#000000'
            },
            areaStyle: {
              color: '#d4d9dd'
            }
          },
          fillerColor: 'rgba(31,178,251,0.2)',
          labelFormatter: function (value, params) {
            var str = ''
            if (params.length > 4) {
              str = params.substring(0, 4) + '人'
            } else {
              str = params
            }
            return str
          }
        }],
        grid: {
          left: '2%',
          right: '2%',
          bottom: '6%',
          top: '14%',
          containLabel: true,
          borderWidth: '0'
        },
        series: [{
          name: '运动员人数',
          type: 'line',
          smooth: true,
          symbol: 'circle',
          symbolSize: 10,
          data: [489, 970, 1422, 1545, 1945, 2500, 3100, 3842, 3345, 4839, 6122, 6828, 6554, 7711, 9520, 9704, 9501, 11300, 12500
          ],
          itemStyle: {
            normal: {
              color: '#007BE5',
              lineStyle: {
                width: 2
              }
            }
          }
        }]
      }
      this.chartInstance.setOption(option)
      this.chartInstance.resize()
    }
    }
}
</script>

<style>

</style>
