/**历届金牌排行榜**/
<template>
  <div class="com-container">
    <div class="com-chart" ref="jpph"></div>
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
    this.chartInstance = this.$echarts.init(this.$refs.jpph)
  },
  updataChart () {
	const textfontsize = this.$refs.jpph.offsetWidth / 600
	// console.log(textfontsize)
    var years = ['第一届', '第二届', '第三届', '第四届', '第五届', '第六届', '第七届', '第八届', '第九届', '第十届', '第十一届', '第十二届', '第十三届', '第十四届', '第十五届', '第十六届', '第十七届', '第十八届', '第十九届'
    ]
    var jdData = [
        ['日本', '印度', '伊朗', '新加坡', '菲律宾', '斯里兰卡', '印度尼西亚', '缅甸'],
        ['日本', '菲律宾', '巴基斯坦', '印度', '中国', '以色列', '缅甸', '韩国', '斯里兰卡', '印度尼西亚'],
        ['日本', '菲律宾', '韩国', '中国', '巴基斯坦', '印度', '伊朗', '越南', '缅甸', '新加坡'],
        ['日本', '印度尼西亚', '印度', '巴基斯坦', '菲律宾', '韩国', '泰国', '马来西亚', '缅甸', '新加坡'],
        ['日本', '韩国', '泰国', '马来西亚', '印度', '印度尼西亚', '伊朗', '中国', '以色列', '菲律宾'],
        ['日本', '韩国', '泰国', '印度尼西亚', '印度', '以色列', '马来西亚', '缅甸', '伊朗', '斯里兰卡'],
        ['日本', '伊朗', '中国', '韩国', '印度尼西亚', '以色列', '印度', '泰国', '朝鲜', '蒙古'],
        ['日本', '中国', '韩国', '朝鲜', '泰国', '印度', '印度尼西亚', '巴基斯坦', '菲律宾', '伊拉克'],
        ['中国', '日本', '韩国', '朝鲜', '印度', '印度尼西亚', '伊朗', '巴基斯坦', '蒙古', '菲律宾'],
        ['中国', '韩国', '日本', '伊朗', '印度', '菲律宾', '泰国', '巴基斯坦', '印度尼西亚', '中国香港'],
        ['中国', '韩国', '日本', '朝鲜', '伊朗', '巴基斯坦', '印度尼西亚', '卡塔尔', '泰国', '马来西亚'],
        ['中国', '日本', '韩国', '乌兹别克斯坦', '伊朗', '中国台北', '印度', '马来西亚', '卡塔尔', '印度尼西亚'],
        ['中国', '日本', '韩国', '泰国', '哈萨克斯坦', '中国台北', '伊朗', '乌兹别克斯坦', '印度', '朝鲜'],
        ['中国', '韩国', '日本', '哈萨克斯坦', '乌兹别克斯坦', '泰国', '中国台北', '印度', '朝鲜', '伊朗'],
        ['中国', '韩国', '日本', '哈萨克斯坦', '泰国', '伊朗', '乌兹别克斯坦', '印度', '卡达尔', '中国台北'],
      ['中国', '韩国', '日本', '伊朗', '哈萨克斯坦', '印度', '中国台北', '乌兹别克斯坦', '泰国', '马来西亚'],
      ['中国', '韩国', '日本', '哈萨克斯坦', '伊朗', '泰国', '朝鲜', '印度', '中国台北', '卡特尔'],
      ['中国', '日本', '韩国', '印度尼西亚', '乌兹别克斯坦', '伊朗', '中国台北', '印度', '哈萨克斯坦', '朝鲜'],
      ['中国', '日本', '韩国', '印度', '乌兹别克斯坦', '中国台北', '伊朗', '泰国', '巴林', '朝鲜']

    ]
    var data = [
        [24, 15, 8, 5, 5, 0, 0, 0],
        [38, 14, 4, 4, 2, 2, 2, 0, 0, 0],
        [67, 8, 8, 6, 6, 5, 4, 2, 2, 1],
        [73, 11, 10, 8, 7, 4, 2, 2, 2, 1],
        [78, 12, 12, 7, 7, 7, 6, 5, 3, 2],
        [75, 36, 32, 16, 15, 7, 4, 4, 3, 2],
        [74, 18, 9, 9, 6, 6, 5, 3, 2, 2],
        [70, 51, 18, 15, 11, 11, 8, 4, 4, 2],
        [61, 57, 28, 17, 13, 4, 4, 3, 3, 2],
        [94, 93, 58, 6, 5, 4, 3, 2, 1, 1],
        [183, 54, 38, 12, 4, 4, 3, 3, 2, 2],
        [125, 64, 63, 10, 9, 7, 4, 4, 4, 3],
        [129, 66, 52, 24, 24, 19, 10, 7, 7, 6],
        [150, 96, 44, 20, 15, 14, 10, 10, 10, 9, 8],
        [166, 58, 50, 23, 13, 11, 11, 10, 9, 9],
        [199, 76, 48, 20, 18, 14, 13, 11, 11, 9],
        [151, 79, 47, 28, 21, 12, 11, 11, 10, 10],
        [132, 75, 49, 31, 21, 20, 17, 15, 15, 12],
        [201, 52, 42, 28, 22, 19, 13, 12, 12, 11]
    ]
    const option = {
        baseOption: {
        backgroundColor: '#F5F5F5',
            timeline: {
                data: years,
                axisType: 'category',
                autoPlay: true,
                playInterval: 2200,
                left: 'center',
                right: '15%',
                bottom: textfontsize + 2,
                width: '95%',
                label: {
                    normal: {
                        textStyle: {
                            color: '#5F3818'
                        }
                    }
                },
                symbolSize: 6,
                lineStyle: {
                    color: '#555'
                },
                checkpointStyle: {
                    borderColor: '#777',
                    borderWidth: 2
                },
                controlStyle: {
                    itemSize: 19,
                    itemGap: 3,
                    normal: {
                        color: '#FFA500',
                        borderColor: '#FFA500'
                    },
                    emphasis: {
                        color: '#FFA500',
                        borderColor: '#FFA500'
                    }
                }
            },
            title: [{
                text: '',
                right: '5%',
                bottom: '15%',
                textStyle: {
                    fontSize: 25,
                    color: '#696969'
                }
            }, {
                text: '历届金牌排行榜',
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
            }],
            tooltip: {
                trigger: 'axis'
            },
            calculable: true,
            grid: {
                left: '4%',
                right: '3%',
                bottom: '12%',
                top: '10%',
                containLabel: true
            },
            label: {
                normal: {
                    textStyle: {
                        color: '#fff'
                    }
                }
            },
            yAxis: [{
                offset: '10',
                type: 'category',
                data: '',
                nameTextStyle: {
                    color: ''
                },
                axisLine: {
                    show: false
                },
                axisTick: {
                    show: false
                },
                axisLabel: {
                    textStyle: {
                        fontSize: 10 + textfontsize
                    }
                }
            }],
            xAxis: [{
                type: 'value',
                splitNumber: 8,
                axisLabel: {
                    formatter: '{value} '
                },
                splitLine: {
                    lineStyle: {
                        color: '#ccc'
                    }
                }
            }],
            series: [{
                type: 'bar',
                barWidth: '50%',
                barBorderRadius: [0, 20, 20, 0],
                label: {
                    normal: {
                        show: true,
                        position: 'inside',
                        formatter: '{c}'
                    }
                },
                itemStyle: {
                    normal: {
                        color: function (params) {
                            var colorList = [
                                '#21EBE3', '#eea2a4', '#f5b971', '#916CFE', '#aacfcf', '#d291bc', '#ffa5b0',
                                '#fedd8b', '#EB5E21', '#a6dcef', '#c3bed4', '#495a80',
                                '#9966cc', '#bdb76a', '#eee8ab', '#a35015',
                                '#04dd98', '#d9b3e6', '#b6c3fc', '#315dbc'
                            ]
                            return colorList[params.dataIndex]
                        }
                    }
                }
            }],
            animationDurationUpdate: 2000,
            animationEasingUpdate: 'quinticInOut'
        },
        options: []
    }
    for (var n = 0; n < years.length; n++) {
        var res = []
        for (var j = 0; j < data[n].length; j++) {
            res.push({
                name: jdData[n][j],
                value: data[n][j]
            })
        }
        res.sort(function (a, b) {
            return b.value - a.value
        }).slice(0, 6)
        res.sort(function (a, b) {
            return a.value - b.value
        })
        var res1 = []
        var res2 = []
        for (var t = 0; t < res.length; t++) {
            res1[t] = res[t].name
            res2[t] = res[t].value
        }
        option.options.push({
            title: {
                text: years[n]
            },
            yAxis: {
                data: res1
            },
            series: [{
                data: res2
            }]
        })
      }
    this.chartInstance.setOption(option)
    this.chartInstance.resize()
  }
 }
}

</script>

<style>

</style>
