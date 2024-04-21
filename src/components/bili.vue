/**历届亚运会参赛国家与项目变化图**/
<template>
  <div class="com-container">
    <div class="com-chart" ref="bili_ref"></div>
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
      this.chartInstance = this.$echarts.init(this.$refs.bili_ref)
    },
    updataChart () {
			// const textfontsize = this.$refs.all_ref.offsetWidth
    const option = {
      backgroundColor: '#F5F5F5',
      title: {
        text: '历届亚运会参赛国家与项目变化图',
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
          type: 'shadow'
        }
      },
      grid: {
        left: '2%',
        right: '2%',
        bottom: '5%',
        top: '17%', // 改
        containLabel: true
      },
      legend: {
        data: ['运动项目个数', '参赛国家/地区'],
        right: 10,
        top: 50,
        textStyle: {
          fontSize: 13,
          color: '#000000'
        },
        itemWidth: 12,
        itemHeight: 10
      },
      xAxis: {
        type: 'category',
        data: ['第一届', '第二届', '第三届', '第四届', '第五届', '第六届', '第七届', '第八届', '第九届', '第十届', '第十一届', '第十二届', '第十三届', '第十四届', '第十五届', '第十六届', '第十七届', '第十八届', '第十九届'
        ],
        axisLine: {
          lineStyle: {
            color: '#000000'
          }
        },
        axisLabel: {
          fontSize: 15
        }
      },
      yAxis: {
        type: 'value',
        max: '100',
        axisLine: {
          show: false,
          lineStyle: {
            color: '#000000'
          }
        },
        axisLabel: {
          fontSize: 15
        }
      },
      dataZoom: [{
        type: 'slider',
        filterMode: 'filter',
        height: 15,
        left: '10%',
        right: '10%',
        xAxisIndex: [
          0
        ],
        bottom: '1%',
        start: 0,
        end: 40,
        handleStyle: {
          color: '#FFFFFF'
        },
        textStyle: {
          color: '#696969'
        },
        borderColor: '#90979c'
      }],
      series: [{
          name: '运动项目个数',
          type: 'bar',
          barWidth: '30%',
          itemStyle: {
            normal: {
              color: new this.$echarts.graphic.LinearGradient(0, 0, 0, 1, [{
                offset: 0,
                color: '#8899FC'
              }, {
                offset: 1,
                color: '#2A49FE'
              }]),
              barBorderRadius: 10
            }
          },
          data: [6, 8, 13, 13, 14, 13, 16, 19, 21, 25, 29, 34, 36, 38, 39, 42, 36, 40, 40]
        },
        {
          name: '参赛国家/地区',
          type: 'bar',
          barWidth: '30%',
          itemStyle: {
            normal: {
              color: new this.$echarts.graphic.LinearGradient(0, 0, 0, 1, [{
                offset: 1,
                color: '#2EDEFF'
              }, {
                offset: 0,
                color: '#88EAFC'
              }]),
              barBorderRadius: 10
            }

          },
          data: [11, 18, 20, 17, 18, 18, 25, 25, 33, 27, 36, 42, 41, 44, 45, 45, 45, 45, 45
          ]
        }
      ]
    }
      this.chartInstance.setOption(option)
      this.chartInstance.resize()
    }
  }
}
</script>

<style>
</style>
