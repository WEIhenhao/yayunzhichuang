/**亚运会发展史***/
<template>
  <div class="com-container">
    <div class="com-chart" ref="map_ref"></div>
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
      this.chartInstance = this.$echarts.init(this.$refs.map_ref)
    },
    updataChart () {
      // const size = this.$refs.map_ref.offsetWidth / 100 * 3.6
      var data = [{
              time: '第一届',
              data: [{
                name: '印度',
                value: [28.6139, 77.209, '印度'],
                year: '1951年',
                address: '新德里',
                countries: '11个',
                events: '6大项，57小项',
                athletes: '489人',
                link: 'https://baike.baidu.com/item/1951%E5%B9%B4%E6%96%B0%E5%BE%B7%E9%87%8C%E4%BA%9A%E8%BF%90%E4%BC%9A/5439088?structureClickId=5439088&structureId=aa3243d2527c861aa52f9885&structureItemId=fe67b47a4a12420207e9925b&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第一届亚运会'
              }]
            }, {
              time: '第二届',
              data: [{
                name: '菲律宾',
                value: [14.5995, 120.9842, '菲律宾'],
                year: '1954年',
                address: '马尼拉',
                countries: '18个',
                events: '8大项，76小项',
                athletes: '2026人',
                link: 'https://baike.baidu.com/item/1954%E5%B9%B4%E9%A9%AC%E5%B0%BC%E6%8B%89%E4%BA%9A%E8%BF%90%E4%BC%9A/5438946?structureClickId=5438946&structureId=aa3243d2527c861aa52f9885&structureItemId=aeb9b7bb13b40f7b3b27205b&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第二届亚运会'
              }]
            }, {
              time: '第三届',
              data: [{
                name: '日本',
                value: [35.6895, 139.6917, '日本'],
                year: '1958年',
                address: '雅加达',
                countries: '20个',
                events: '13大项，97小项',
                athletes: '1422人',
                link: 'https://baike.baidu.com/item/1958%E5%B9%B4%E4%B8%9C%E4%BA%AC%E4%BA%9A%E8%BF%90%E4%BC%9A/5571856?structureClickId=5571856&structureId=aa3243d2527c861aa52f9885&structureItemId=703153e222fbf9c87b05f722&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第三届亚运会'
              }]
            }, {
              time: '第四届',
              data: [{
                name: '印度尼西亚',
                value: [6.2088, 106.8456, '印度尼西亚'],
                year: '1962年',
                address: '雅加达',
                countries: '17个',
                events: '13大项，120小项',
                athletes: '1545人',
                link: 'https://baike.baidu.com/item/1962%E5%B9%B4%E9%9B%85%E5%8A%A0%E8%BE%BE%E4%BA%9A%E8%BF%90%E4%BC%9A/5572073?structureClickId=5572073&structureId=aa3243d2527c861aa52f9885&structureItemId=60005a461351256713e12e23&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第四届亚运会'
              }]
            }, {
              time: '第五届',
              data: [{
                name: '泰国',
                value: [13.7563, 100.5018, '泰国'],
                year: '1966年',
                address: '曼谷',
                countries: '18个',
                events: '14大项，143小项',
                athletes: '1945人',
                link: 'https://baike.baidu.com/item/1966%E5%B9%B4%E6%9B%BC%E8%B0%B7%E4%BA%9A%E8%BF%90%E4%BC%9A/5571752?structureClickId=5571752&structureId=aa3243d2527c861aa52f9885&structureItemId=e3ce1325665821e731416f22&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第五届亚运会'
              }]
            }, {
              time: '第六届',
              data: [{
                name: '泰国',
                value: [13.7563, 100.5018, '泰国'],
                year: '1970年',
                address: '曼谷',
                countries: '18个',
                events: '13大项，135小项',
                athletes: '2500人',
                link: 'https://baike.baidu.com/item/1970%E5%B9%B4%E6%9B%BC%E8%B0%B7%E4%BA%9A%E8%BF%90%E4%BC%9A/5439390?structureClickId=5439390&structureId=aa3243d2527c861aa52f9885&structureItemId=5c29a1b977d926f14c877c25&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第六届亚运会'
              }]
            }, {
              time: '第七届',
              data: [{
                name: '伊朗',
                value: [35.6892, 51.3890, '伊朗'],
                year: '1974年',
                address: '德黑兰',
                countries: '25个',
                events: '17个大项,185个小项',
                athletes: '3100人',
                link: 'https://baike.baidu.com/item/1974%E5%B9%B4%E5%BE%B7%E9%BB%91%E5%85%B0%E4%BA%9A%E8%BF%90%E4%BC%9A/5439310?structureClickId=5439310&structureId=aa3243d2527c861aa52f9885&structureItemId=427d0d5a0bd587c9065bcc24&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第七届亚运会'
              }]
            }, {
              time: '第八届',
              data: [{
                name: '泰国',
                value: [13.7563, 100.5018, '泰国'],
                year: '1978年',
                address: '曼谷',
                countries: '25个',
                events: '19大项，201小项',
                athletes: '3842人',
                link: 'https://baike.baidu.com/item/1978%E5%B9%B4%E6%9B%BC%E8%B0%B7%E4%BA%9A%E8%BF%90%E4%BC%9A/5439224?structureClickId=5439224&structureId=aa3243d2527c861aa52f9885&structureItemId=013e9d86d304c2966d2a1a24&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第八届亚运会'
              }]
            }, {
              time: '第九届',
              data: [{
                name: '印度',
                value: [28.6139, 77.209, '印度'],
                year: '1982年',
                address: '新德里',
                countries: '33个',
                events: '21大项，196小项',
                athletes: '3345人',
                link: 'https://baike.baidu.com/item/1982%E5%B9%B4%E6%96%B0%E5%BE%B7%E9%87%8C%E4%BA%9A%E8%BF%90%E4%BC%9A/5439159?structureClickId=5439159&structureId=aa3243d2527c861aa52f9885&structureItemId=52088533a743eaec3bc55b24&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第九届亚运会'
              }]
            }, {
              time: '第十届',
              data: [{
                name: '韩国',
                value: [37.5665, 126.9780, '韩国'],
                year: '1986年',
                address: '汉城',
                countries: '27个',
                events: '25大项',
                athletes: '4839人',
                link: 'https://baike.baidu.com/item/1986%E5%B9%B4%E6%B1%89%E5%9F%8E%E4%BA%9A%E8%BF%90%E4%BC%9A/5438875?structureClickId=5438875&structureId=aa3243d2527c861aa52f9885&structureItemId=dfe13240e28b0f68beb97f5b&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第十届亚运会'
              }]
            }, {
              time: '第十一届',
              data: [{
                name: '中国',
                value: [39.9042, 116.4074, '中国'],
                year: '1990年',
                address: '北京',
                countries: '37个',
                events: '29大项，310小项',
                athletes: '6122人',
                link: 'https://baike.baidu.com/item/1990%E5%B9%B4%E5%8C%97%E4%BA%AC%E4%BA%9A%E8%BF%90%E4%BC%9A/5438808?structureClickId=5438808&structureId=aa3243d2527c861aa52f9885&structureItemId=da61672eb91f45bffef3ba5a&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第十一届亚运会'
              }]
            }, {
              time: '第十二届',
              data: [{
                name: '日本',
                value: [34.3853, 132.4553, '日本'],
                year: '1994年',
                address: '广岛',
                countries: '42个',
                events: '34大项，337小项',
                athletes: '6828人',
                link: 'https://baike.baidu.com/item/1994%E5%B9%B4%E5%B9%BF%E5%B2%9B%E4%BA%9A%E8%BF%90%E4%BC%9A/5438655?structureClickId=5438655&structureId=aa3243d2527c861aa52f9885&structureItemId=5a65aebde857b0206976435a&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第十二届亚运会'
              }]
            }, {
               time: '第十三届',
                data: [{
                name: '泰国',
                value: [13.7563, 100.5018, '泰国'],
                year: '1998年',
                address: '曼谷',
                countries: '41个',
                events: '36大项，376小项',
                athletes: '6554人',
                link: 'https://baike.baidu.com/item/1998%E5%B9%B4%E6%9B%BC%E8%B0%B7%E4%BA%9A%E8%BF%90%E4%BC%9A/5438302?structureClickId=5438302&structureId=aa3243d2527c861aa52f9885&structureItemId=91862abafda8be87950abc58&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第十三届亚运会'
              }]
            }, {
              time: '第十四届',
              data: [{
                name: '韩国',
                value: [35.1796, 129.0756, '韩国'],
                year: '2002年',
                address: '釜山',
                countries: '44个',
                events: '38大项，419小项',
                athletes: '7711人',
                link: 'https://baike.baidu.com/item/2002%E5%B9%B4%E9%87%9C%E5%B1%B1%E4%BA%9A%E8%BF%90%E4%BC%9A/5438248?structureClickId=5438248&structureId=aa3243d2527c861aa52f9885&structureItemId=9a7035920e287d3e50cdea58&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第十四届亚运会'
              }]
            }, {
              time: '第十五届',
              data: [{
                name: '卡塔尔',
                value: [25.2769, 51.5185, '卡塔尔'],
                year: '2006年',
                address: '多哈',
                countries: '45个',
                events: '39大项，424小项',
                athletes: '9520人',
                link: 'https://baike.baidu.com/item/2006%E5%B9%B4%E5%A4%9A%E5%93%88%E4%BA%9A%E8%BF%90%E4%BC%9A/5438166?structureClickId=5438166&structureId=aa3243d2527c861aa52f9885&structureItemId=624e65aca79d4c8856133458&lemmaFrom=starMapContent_star&fromModule=starMap_content&lemmaIdFrom=5571856',
                years: '第十五届亚运会'
              }]
            }, {
              time: '第十六届',
                data: [{
                name: '中国',
                value: [23.1291, 113.2644, '中国'],
                year: '2010年',
                address: '广州',
                countries: '45个',
                events: '42大项，476小项',
                athletes: '9704人',
                link: 'https://baike.sogou.com/v48123.htm?ch=frombaikevr&fromTitle=2010%E5%B9%B4%E5%B9%BF%E5%B7%9E%E4%BA%9A%E8%BF%90%E4%BC%9A',
                years: '第十六届亚运会'
              }]
            }, {
              time: '第十七届',
              data: [{
                name: '韩国',
                value: [37.4563, 126.7052, '韩国'],
                year: '2014年',
                address: '仁川',
                countries: '45个',
                events: '36大项，439小项',
                athletes: '9501人',
                link: 'https://baike.sogou.com/v11023075.htm?ch=frombaikevr&fromTitle=2014%E5%B9%B4%E4%BB%81%E5%B7%9D%E4%BA%9A%E8%BF%90%E4%BC%9A',
                years: '第十七届亚运会'
              }]
            }, {
              time: '第十八届',
              data: [{
                name: '印度尼西亚',
                value: [6.2088, 106.8456, '印度尼西亚'],
                year: '2018年',
                address: '雅加达',
                countries: '45个',
                events: '40大项，465小项',
                athletes: '11300人',
                link: 'https://baike.sogou.com/v81094511.htm?ch=frombaikevr&fromTitle=2018%E5%B9%B4%E9%9B%85%E5%8A%A0%E8%BE%BE%E4%BA%9A%E8%BF%90%E4%BC%9A',
                years: '第十八届亚运会'
              }]
            }, {
              time: '第十九届',
              data: [{
                name: '中国',
                value: [30.2741, 120.1551, '中国'],
                year: '2023年',
                address: '杭州',
                countries: '45个',
                events: '40个大项，61个分项，481个小项',
                athletes: '17492人',
                link: 'https://baike.sogou.com/v106136485.htm',
                years: '第十三届亚运会'
              }]
            }
            ]
           const option = {
              baseOption: {
                animationDurationUpdate: 1000,
                animationEasingUpdate: 'quinticInOut',
                timeline: {
                  axisType: 'category',
                  autoPlay: true,
                  playInterval: 2000,
                  left: 'center',
                  bottom: '2%',
                  width: '95%',
                  label: {
                    normal: {
                      textStyle: {
                        color: '#696969'
                      }
                    },
                    position: 'top'
                  },
                  lineStyle: {
                    color: '#696969'
                  },
                  symbolSize: 10,
                  checkpointStyle: {
                    borderColor: '#8df4f4',
                    color: '#53D9FF',
                    borderWidth: 5
                  },
                  controlStyle: {
                    itemSize: 25,
                    itemGap: 2,
                    normal: {
                      borderColor: '#696969'
                    }
                  },
                  data: data.map(function (ele) {
                    return ele.time
                  })
                },
                backgroundColor: '#F5F5F5',
                title: {
                  text: '亚运会发展史',
                  subtext: '数据来源：百度百科',
                  x: 'center',
                  y: '3%',
                  textStyle: {
                    fontFamily: 'sans-serif',
                    fontSize: 22,
                    fontWeight: 'normal'
                  },
                  subtextStyle: {
                    color: '#646464',
                    fontFamily: 'sans-serif',
                    fontSize: 16,
                    fontWeight: 'normal'
                  }
                },
                tooltip: {
                  trigger: 'item',
                  type: 'line',
                  triggerOn: 'none',
                  formatter: function (params) {
                    if (params.data) {
                      return '&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;' + params.data.years + '<br><br>' +
                        params
                        .marker + '举办时间：' + params.data.year + '<br><br>' + params.marker + '举办地点：' + params
                        .data.value[2] + '—' + params.data.address + '<br><br>' + params.marker +
                        '代表国家/地区数：' +
                        params.data.countries + '<br><br>' + params.marker + '比赛项目：' + params.data.events +
                        '<br><br>' + params.marker + '参赛人数：' + params.data.athletes
                    }
                  }
                },
                series: [{
                  id: 'map',
                  type: 'map',
                  mapType: 'world',
                  zoom: 1.23,
                  roam: true,
                  nameMap: {
                    Afghanistan: '阿富汗',
                    Singapore: '新加坡',
                    Angola: '安哥拉',
                    Albania: '阿尔巴尼亚',
                    'United Arab Emirates': '阿联酋',
                    Argentina: '阿根廷',
                    Armenia: '亚美尼亚',
                    'French Southern and Antarctic Lands': '法属南半球和南极领地',
                    Australia: '澳大利亚',
                    Austria: '奥地利',
                    Azerbaijan: '阿塞拜疆',
                    Burundi: '布隆迪',
                    Belgium: '比利时',
                    Benin: '贝宁',
                    'Burkina Faso': '布基纳法索',
                    Bangladesh: '孟加拉国',
                    Bulgaria: '保加利亚',
                    'The Bahamas': '巴哈马',
                    'Bosnia and Herzegovina': '波斯尼亚和黑塞哥维那',
                    Belarus: '白俄罗斯',
                    Belize: '伯利兹',
                    Bermuda: '百慕大',
                    Bolivia: '玻利维亚',
                    Brazil: '巴西',
                    Brunei: '文莱',
                    Bhutan: '不丹',
                    Botswana: '博茨瓦纳',
                    'Central African Republic': '中非共和国',
                    Canada: '加拿大',
                    Switzerland: '瑞士',
                    Chile: '智利',
                    China: '中国',
                    'Ivory Coast': '象牙海岸',
                    Cameroon: '喀麦隆',
                    'Democratic Republic of the Congo': '刚果民主共和国',
                    'Republic of the Congo': '刚果共和国',
                    Colombia: '哥伦比亚',
                    'Costa Rica': '哥斯达黎加',
                    Cuba: '古巴',
                    'Northern Cyprus': '北塞浦路斯',
                    Cyprus: '塞浦路斯',
                    'Czech Republic': '捷克共和国',
                    Germany: '德国',
                    Djibouti: '吉布提',
                    Denmark: '丹麦',
                    'Dominican Republic': '多明尼加共和国',
                    Algeria: '阿尔及利亚',
                    Ecuador: '厄瓜多尔',
                    Egypt: '埃及',
                    Eritrea: '厄立特里亚',
                    Spain: '西班牙',
                    Estonia: '爱沙尼亚',
                    Ethiopia: '埃塞俄比亚',
                    Finland: '芬兰',
                    Fiji: '斐',
                    'Falkland Islands': '福克兰群岛',
                    France: '法国',
                    Gabon: '加蓬',
                    'United Kingdom': '英国',
                    Georgia: '格鲁吉亚',
                    Ghana: '加纳',
                    Guinea: '几内亚',
                    Gambia: '冈比亚',
                    'Guinea Bissau': '几内亚比绍',
                    Greece: '希腊',
                    Greenland: '格陵兰',
                    Guatemala: '危地马拉',
                    'French Guiana': '法属圭亚那',
                    Guyana: '圭亚那',
                    Honduras: '洪都拉斯',
                    Croatia: '克罗地亚',
                    Haiti: '海地',
                    Hungary: '匈牙利',
                    Indonesia: '印度尼西亚',
                    India: '印度',
                    Ireland: '爱尔兰',
                    Iran: '伊朗',
                    Iraq: '伊拉克',
                    Iceland: '冰岛',
                    Israel: '以色列',
                    Italy: '意大利',
                    Jamaica: '牙买加',
                    Jordan: '约旦',
                    Japan: '日本',
                    Kazakhstan: '哈萨克斯坦',
                    Kenya: '肯尼亚',
                    Kyrgyzstan: '吉尔吉斯斯坦',
                    Cambodia: '柬埔寨',
                    Kosovo: '科索沃',
                    Kuwait: '科威特',
                    Laos: '老挝',
                    Lebanon: '黎巴嫩',
                    Liberia: '利比里亚',
                    Libya: '利比亚',
                    'Sri Lanka': '斯里兰卡',
                    Lesotho: '莱索托',
                    Lithuania: '立陶宛',
                    Luxembourg: '卢森堡',
                    Latvia: '拉脱维亚',
                    Morocco: '摩洛哥',
                    Moldova: '摩尔多瓦',
                    Madagascar: '马达加斯加',
                    Mexico: '墨西哥',
                    Macedonia: '马其顿',
                    Mali: '马里',
                    Myanmar: '缅甸',
                    Montenegro: '黑山',
                    Mongolia: '蒙古',
                    Mozambique: '莫桑比克',
                    Mauritania: '毛里塔尼亚',
                    Malawi: '马拉维',
                    Malaysia: '马来西亚',
                    Namibia: '纳米比亚',
                    'New Caledonia': '新喀里多尼亚',
                    Niger: '尼日尔',
                    Nigeria: '尼日利亚',
                    Nicaragua: '尼加拉瓜',
                    Netherlands: '荷兰',
                    Norway: '挪威',
                    Nepal: '尼泊尔',
                    'New Zealand': '新西兰',
                    Oman: '阿曼',
                    Pakistan: '巴基斯坦',
                    Panama: '巴拿马',
                    Peru: '秘鲁',
                    Philippines: '菲律宾',
                    'Papua New Guinea': '巴布亚新几内亚',
                    Poland: '波兰',
                    'Puerto Rico': '波多黎各',
                    'North Korea': '北朝鲜',
                    Portugal: '葡萄牙',
                    Paraguay: '巴拉圭',
                    Qatar: '卡塔尔',
                    Romania: '罗马尼亚',
                    Russia: '俄罗斯',
                    Rwanda: '卢旺达',
                    'Western Sahara': '西撒哈拉',
                    'Saudi Arabia': '沙特阿拉伯',
                    Sudan: '苏丹',
                    'South Sudan': '南苏丹',
                    Senegal: '塞内加尔',
                    'Solomon Islands': '所罗门群岛',
                    'Sierra Leone': '塞拉利昂',
                    'El Salvador': '萨尔瓦多',
                    Somaliland: '索马里兰',
                    Somalia: '索马里',
                    'Republic of Serbia': '塞尔维亚',
                    Suriname: '苏里南',
                    Slovakia: '斯洛伐克',
                    Slovenia: '斯洛文尼亚',
                    Sweden: '瑞典',
                    Swaziland: '斯威士兰',
                    Syria: '叙利亚',
                    Chad: '乍得',
                    Togo: '多哥',
                    Thailand: '泰国',
                    Tajikistan: '塔吉克斯坦',
                    Turkmenistan: '土库曼斯坦',
                    'East Timor': '东帝汶',
                    'Trinidad and Tobago': '特里尼达和多巴哥',
                    Tunisia: '突尼斯',
                    Turkey: '土耳其',
                    'United Republic of Tanzania': '坦桑尼亚',
                    Uganda: '乌干达',
                    Ukraine: '乌克兰',
                    Uruguay: '乌拉圭',
                    'United States': '美国',
                    Uzbekistan: '乌兹别克斯坦',
                    Venezuela: '委内瑞拉',
                    Vietnam: '越南',
                    Vanuatu: '瓦努阿图',
                    'West Bank': '西岸',
                    Yemen: '也门',
                    'South Africa': '南非',
                    Zambia: '赞比亚',
                    Korea: '韩国',
                    Tanzania: '坦桑尼亚',
                    Zimbabwe: '津巴布韦',
                    Congo: '刚果',
                    'Central African Rep.': '中非',
                    Serbia: '塞尔维亚',
                    'Bosnia and Herz.': '波黑',
                    'Czech Rep.': '捷克',
                    'W. Sahara': '西撒哈拉',
                    'Lao PDR': '老挝',
                    'Dem.Rep.Korea': '朝鲜',
                    'Falkland Is.': '福克兰群岛',
                    'Timor-Leste': '东帝汶',
                    'Solomon Is.': '所罗门群岛',
                    Palestine: '巴勒斯坦',
                    'N. Cyprus': '北塞浦路斯',
                    Aland: '奥兰群岛',
                    'Fr. S. Antarctic Lands': '法属南半球和南极陆地',
                    Mauritius: '毛里求斯',
                    Comoros: '科摩罗',
                    'Eq. Guinea': '赤道几内亚',
                    'Guinea-Bissau': '几内亚比绍',
                    'Dominican Rep.': '多米尼加',
                    'Saint Lucia': '圣卢西亚',
                    Dominica: '多米尼克',
                    'Antigua and Barb.': '安提瓜和巴布达',
                    'U.S. Virgin Is.': '美国原始岛屿',
                    Montserrat: '蒙塞拉特',
                    Grenada: '格林纳达',
                    Barbados: '巴巴多斯',
                    Samoa: '萨摩亚',
                    Bahamas: '巴哈马',
                    'Cayman Is.': '开曼群岛',
                    'Faeroe Is.': '法罗群岛',
                    'IsIe of Man': '马恩岛',
                    Malta: '马耳他共和国',
                    Jersey: '泽西',
                    'Cape Verde': '佛得角共和国',
                    'Turks and Caicos Is.': '特克斯和凯科斯群岛',
                    'St. Vin. and Gren.': '圣文森特和格林纳丁斯'
                  },
                  itemStyle: {
                    normal: {
                      areaColor: '#F0FFFF',
                      borderColor: '#87CEFA',
                      borderWidth: 0.8
                    },
                    emphasis: {
                      areaColor: '#D3D3D3'
                    }
                  },
                  label: {
                    emphasis: { //  对应的鼠标悬浮效果
                      show: true,
                      textStyle: {
                        color: '#FF0000'
                      }
                    }
                  },
                  data: []
                }]
              },
              options: []
            }
            for (var i = 0; i < data.length; i++) {
              //  计
              option.options.push({
                visualMap: [{
                  show: false,
                  dimension: 0,
                  left: '25%',
                  // min: data[i].data[9].value[0],
                  // max: data[i].data[0].value[0],
                  inRange: {
                    color: ['#808080', '#F93F16']
                  }
                }],
                series: [{
                  data: data[i].data
                }]
              })
            }
            this.chartInstance.setOption(option)
            // const mTime =
            setInterval(() => {
              this.chartInstance.dispatchAction({
                type: 'showTip',
                seriesIndex: 0,
                dataIndex: 0
              })
            }, 1000)
            this.chartInstance.on('click', function (param) {
              if (param.data.link) {
                window.open(param.data.link)
              }
            })
      // this.chartInstance.setOption(option)
      this.chartInstance.resize()
    }
  }
}
</script>

<style>
</style>
