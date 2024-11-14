<template>
    <!-- <div id="myChart" ref="myChart" style="width: 100%;height:480px;"></div> -->
    <div class="home">
        <div class="home-tb">
            <h2>康必恩BI看板</h2>
            <div class="time">
                <div class="yaer-box">
                    <label for="yearSelect">年份</label>
                    <select id="yearSelect" name="yearSelect">
                        <option value="2000">2000</option>
                        <option value="2001">2001</option>
                        <option value="2002">2002</option>
                        <option value="2023">2023</option>
                        <option value="2024">2024</option>
                    </select>
                </div>
                <div class="yuefen">
                    <label for="monthSelect">月份</label>
                    <select id="monthSelect" name="monthSelect">
                        <option value="1">1月</option>
                        <option value="2">2月</option>
                        <option value="3">3月</option>
                        <option value="4">4月</option>
                        <option value="5">5月</option>
                        <option value="6">6月</option>
                        <option value="7">7月</option>
                        <option value="8">8月</option>
                        <option value="9">9月</option>
                        <option value="10">10月</option>
                        <option value="11">11月</option>
                        <option value="12">12月</option>
                    </select>
                </div>
                <span class="btn">确定</span>
            </div>
        </div>
        <div class="home-db">
            <div class="home-left">
                <div class="home-left1">

                    <div class="zb">
                        <div class="sb">
                            <arrowRight />
                            <span class="ddzl">
                                订单总量
                            </span>
                        </div>
                        <div class="xb">
                            288
                        </div>
                    </div>
                    <div class="yb">
                        <div id="myChart" ref="myChart" style="width: 100%;height:100%;"></div>
                    </div>
                </div>
                <div class="home-left2">
                    <Card title="出库排名TOP5">
                        <div id="TOP5Chart" ref="TOP5Chart" style="width: 100%;height:100%;"></div>
                    </Card>

                </div>
                <div class="home-left3">
                    <Card title="入库/留样合格率">
                        <div id="rkChart" ref="rkChart" style="width: 100%;height:100%;"></div>
                    </Card>
                </div>
            </div>
            <div class="home-mid">
                <div class="home-mid-tb">
                    <arrowRight />
                    <span class="gcsxl">各城市销量</span>
                </div>
                <div class="home-mid-zm">
                    <div class="circle1">
                        <div class="line"></div>
                        <span class="nc">南昌</span>
                        <span class="num">1688</span>
                    </div>
                    <div class="circle2">
                        <div class="line"></div>
                        <span class="nc">上海</span>
                        <span class="num">1759</span>
                    </div>
                    <div class="circle3">
                        <div class="line"></div>
                        <span class="nc">香港</span>
                        <span class="num">1634</span>
                    </div>
                    <div class="circle4">
                        <div class="line"></div>
                        <span class="nc">德国</span>
                        <span class="num">2011</span>
                    </div>
                </div>
                <div class="home-mid-db">
                    <div class="kcxx-box">
                        <arrowRight />
                        <span class="kcxx">各城市销量</span>
                    </div>
                    <div class="bfb-box">
                        <div class="bfb-item bft1">
                            <span class="tt">原材料库位</span>
                            <span class="bl1">84%</span>
                            <span class="yyl">库位量 438</span>
                            <span class="yyl">已用量 368</span>
                        </div>
                        <div class="bfb-item bft2">
                            <span class="tt">半成品库位</span>
                            <span class="bl2">78%</span>
                            <span class="yyl">库位量 266</span>
                            <span class="yyl">已用量 208</span>
                        </div>
                        <div class="bfb-item bft3">
                            <span class="tt">成品库位</span>
                            <span class="bl3">63%</span>
                            <span class="yyl">库位量 1560</span>
                            <span class="yyl">已用量 988</span>
                        </div>
                    </div>
                </div>
            </div>

            <div class="home-right">
                <div class="home-left1">
                    <div class="qxxs">
                        <arrowRight />
                        <span class="qxxs-text">安全运行天数</span>
                    </div>
                    <div class="wsgxs-box">
                        <div class="wsgxs-left">
                            <span>康必恩仓库</span>
                            <span>无事故天数</span>
                        </div>
                        <div class="wsgxs-right">
                            <span class="ts">308</span>
                            <span class="tian">天</span>
                        </div>
                    </div>


                </div>
                <div class="home-left2">
                    <Card title="库存物资排行TOP5">
                        <div id="kcwzChart" ref="kcwzChart" style="width: 100%;height:100%;"></div>
                    </Card>

                </div>
                <div class="home-left3">
                    <Card title="盘点准确率">
                        <div id="jdtChart" ref="jdtChart" style="width: 100%;height:100%;"></div>
                    </Card>
                </div>
            </div>
        </div>

    </div>
</template>

<script>
import Card from '@/components/Card.vue'
import arrowRight from '@/components/arrowRight.vue';
export default {
    name: 'HelloWorld',
    components: {
        Card, arrowRight
    },
    data() {
        return {
            yaerValue: '',
            newData: [

                {
                    "value": 25,

                },
                {
                    "value": 90,

                }
            ],

        }
    },
    methods: {
        getChart() {
            // 在步骤2的方法1中 通过 this.$echarts.init方法初始化echarts实例并使用 setOption 方法注册图表配置项和数据
            let myChart = this.$echarts.init(document.getElementById("myChart"));
            myChart.setOption({

                color: ['rgb(255, 192, 0)', 'rgb(237, 125, 49)'],

                title: {
                    text: '已完成',
                    textStyle: {
                        color: 'rgb(190, 144, 8)',
                        fontSize: 13,
                    },
                    subtext: '82%',
                    subtextStyle: {
                        fontSize: 13,
                        color: 'rgb(190, 144, 8)',
                        fontWeight: 'bold'
                    },
                    x: 'center',
                    y: '30%',
                },

                grid: {
                    top: '1%',
                    right: '1%',
                    bottom: '8%',
                    left: '1%',
                    containLabel: true
                },
                legend: {
                    orient: 'horizontal',
                    left: 'center',
                    bottom: '7%',
                    textStyle: {
                        color: '#FFF',
                        fontSize: 16,
                    },
                    itemGap: 18,
                    itemWidth: 12,
                    itemHeight: 12,
                    data: this.newData && this.newData.length > 0 ? this.newData : [],
                },
                series: [
                    // 主要展示层的
                    {
                        radius: ['50%', '80%'],
                        center: ['50%', '43%'],
                        type: 'pie',
                        label: {
                            position: 'inner',
                            color: '#6ddcf3',
                            fontSize: 14,
                            // formatter: (item) => {
                            //    return item.data.percentage + '%';
                            // },
                        },
                        data: this.newData && this.newData.length > 0 ? this.newData : [],

                    }
                ]
            });
        },
        getChartTop5() {
            let TOP5Chart = this.$echarts.init(document.getElementById("TOP5Chart"));
            let information = {
                colorArrays: [
                    {
                        flag: "rgb(245,34,45)",
                        top: "rgba(245,34,45,0.75)",
                        bottom: "rgba(114,46,206,0.4)",
                    },
                    {
                        flag: "rgb(250, 140, 22)",
                        top: " rgba(250, 140, 22, 0.75)",
                        bottom: " rgba(160, 217, 17, 0.4)",
                    },
                    {
                        flag: "rgb(82, 196, 26)",
                        top: " rgba(82, 196, 26, 0.75)",
                        bottom: "rgba(160, 217, 17, 0.4)",
                    },
                    {
                        flag: "rgb(19, 194, 194)",
                        top: " rgba(19, 194, 194, 0.75)",
                        bottom: "rgba(47, 84, 235, 0.4)",
                    },
                ],
                legend: [
                    "德国bwodown",
                    "德国男士复合维生素",
                    "K2D3复合胶囊",
                    "安美奇",
                    "胖甘肽小白片",

                ],
                data: [2500, 1500, 1380, 1008, 180],
            };
            TOP5Chart.setOption({

                title: {

                    textStyle: {
                        fontSize: 12,
                        color: "#fff",
                    },
                    right: 30,
                    top: 55,
                },
                tooltip: {
                    show: true,
                    trigger: "axis",
                    formatter: "{b}:{c}",
                    backgroundColor: "rgba(9,40,84,0.8)",
                    borderColor: "rgba(9,40,84,0.8)",
                    textStyle: {
                        fontSize: 10,
                        color: "#fff",
                    },
                    axisPointer: {
                        type: "shadow",
                    },

                },
                grid: {
                    left: "0",
                    top: "3%",
                    right: "10%",
                    bottom: "8%",
                    containLabel: true,
                },
                xAxis: {
                    type: "value",
                    show: false,
                    position: "top",
                    axisTick: {
                        show: false,
                    },
                    axisLine: {
                        show: false,
                    },
                    splitLine: {
                        show: false,
                    },
                },
                yAxis: {
                    type: "category",
                    // name: "单位：kWh/㎡",
                    nameLocation: "start",
                    nameTextStyle: {
                        color: "#b4e4ff",
                        fontSize: 20,
                        padding: [0, 0, 0, 140],
                    },
                    axisTick: {
                        show: false,
                        alignWithLabel: false,
                        length: 5,
                    },
                    splitLine: {
                        //网格线
                        show: false,
                    },
                    inverse: "true", //排序
                    axisLine: {
                        show: true,
                        lineStyle: {
                            color: "rgba(180, 228, 255, 0.3)",
                            width: 2,
                        },
                    },

                    axisLabel: {
                        color: "#fff",
                        margin: 5,
                        fontSize: 10,
                    },
                    data: information.legend,
                },
                series: [
                    {
                        name: "能耗值",
                        type: "bar",
                        stack: "地点",
                        label: {
                            show: true,
                            position: "right",
                            formatter: "{c}",
                            // color: "#b4e4ff", //color of value
                            fontSize: 8,
                            padding: [0, 0, 0, 10],
                        },
                        itemStyle: {
                            show: true,
                            color: "rgb(39, 139, 232)",
                            borderWidth: 0,
                            borderColor: "#333",
                        },
                        emphasis: {
                            // 解决渐变色hover变色问题
                            disabled: true,
                        },
                        barGap: "0%",
                        barCategoryGap: "50%",
                        data: information.data,
                    },

                ],
            })
        },
        getrkChart() {
            let rkChart = this.$echarts.init(document.getElementById("rkChart"));

            rkChart.setOption({
                legend: {
                    top: '5%',
                    right: '10%',
                    icon: 'rect', // 更改图例图标样式为矩形
                    textStyle: {
                        color: '#fff' // 更改图例文本的字体颜色
                    }

                },
                tooltip: {
                    show: true,
                    trigger: 'axis',
                    backgroundColor: 'rgba(255,255,255)',
                },
                grid: {
                    top: '18%',
                    left: '9%',
                    right: '18%',
                    bottom: '30%',
                },
                xAxis: {
                    type: "category",
                    axisLabel: {
                        padding: [0, 10, 0, 0],
                        interval: 0,
                        textStyle: {
                            color: '#fff',
                            fontSize: 12,
                        }
                    },
                    data: ["6月份", "7月份", "8月份", "9月份"] // 明确指定 X 轴的数据
                },
                yAxis: [
                    {
                        type: 'value',
                        min: 0,
                        splitNumber: 6,
                        splitLine: { show: true },
                        axisLabel: {
                            show: true,
                            textStyle: {
                                color: '#fff',
                                fontSize: 14,
                            }
                        },
                        axisLine: {
                            show: false,
                        },
                        axisTick: {
                            show: false,
                        },
                        splitLine: {
                            lineStyle: {
                                color: 'rgba(131,101,101,0.2)',
                                type: 'dashed',
                            }
                        },
                        show: true,
                    },
                    {
                        type: "value",
                        max: 100,
                        // name: "合格率 (%)",
                        nameLocation: 'middle',
                        nameGap: 40,
                        nameTextStyle: {
                            color: "#666666"
                        },
                        position: "right",
                        axisLine: {
                            lineStyle: {
                                color: '#cdd5e2'
                            }
                        },
                        splitLine: {
                            show: false,
                        },
                        axisLabel: {
                            show: true,
                            formatter: "{value} %",
                            textStyle: {
                                // 右侧字体
                                color: "#fff",
                                fontSize: 14,
                            }
                        }
                    }
                ],
                series: [
                    {
                        type: "bar",
                        name: "入库量",
                        data: [2313, 1890, 2019, 2233], // 入库量数据
                        color: "rgb(225, 183, 14)",
                        barWidth: '40%' // 设置柱状图的宽度为柱间距的 40%
                    },
                    {
                        type: "line",
                        name: "留样合格率",
                        yAxisIndex: 1,
                        data: [56, 23, 66, 70], // 合格率数据
                        smooth: true,
                        symbol: "circle",
                        symbolSize: 8,
                        itemStyle: {
                            color: 'rgb(32, 120, 199)'
                        },
                        lineStyle: {
                            color: "rgb(33, 121, 202)"
                        },


                    }
                ],
                color: ["rgb(225, 183, 14)", "rgb(32, 120, 199)"]
            });
        },
        getkcwzChart() {
            let kcwzChart = this.$echarts.init(document.getElementById("kcwzChart"));

            kcwzChart.setOption({

                animation: true,
                grid: {
                    top: "5%",
                    bottom: "15%",
                    right: "5%"
                },
                tooltip: {
                    show: true,
                },
                xAxis: {
                    data: ['德国bwodown',
                        '德国男士复合维生素',
                        'K2D3复合胶囊',
                        '安美奇',
                        '胖甘肽小白片'],
                    axisLine: {
                        show: false //隐藏X轴轴线
                    },
                    axisTick: {
                        show: false //隐藏X轴轴线
                    },
                    rotate: 45,
                    splitLine: {
                        show: true,
                        lineStyle: {
                            color: "rgba(77, 128, 254, 0.2)",
                            width: 2
                        }
                    },
                    axisLabel: {
                        show: true,
                        interval: 0,
                        // margin: 14,
                        fontSize: 9,
                        textStyle: {
                            color: "#a8d5ff", //X轴文字颜色

                        }
                    }
                },
                yAxis: [
                    {
                        type: "value",
                        gridIndex: 0,
                        min: 0,
                        //max: 100,
                        interval: 100,
                        // splitNumber: 4,
                        splitLine: {
                            show: true,
                            lineStyle: {
                                color: "rgba(77, 128, 254, 0.2)",
                                width: 2
                            }
                        },
                        axisTick: {
                            show: false
                        },
                        axisLine: {
                            show: true,
                            lineStyle: {
                                color: "rgba(77, 128, 254, 0.2)"
                            }
                        },
                        axisLabel: {
                            show: true,
                            margin: 14,
                            fontSize: 13,
                            textStyle: {
                                color: "#a8d5ff"
                            }
                        }
                    }
                ],
                series: [
                    {
                        name: "设备在线率",
                        type: "bar",
                        barWidth: 16,
                        itemStyle: {
                            normal: {
                                label: {
                                    show: true, //开启显示
                                    position: 'top', //在上方显示
                                    textStyle: { //数值样式
                                        color: '#fff',
                                        fontSize: 16
                                    }
                                },
                                // color: new echarts.graphic.LinearGradient(0, 0, 0, 1, [
                                //     {
                                //         offset: 0,
                                //         color: "rgba(146, 225, 255, 1)"
                                //     },
                                //     {
                                //         offset: 1,
                                //         color: "rgba(0, 151, 251, 1)"
                                //     }
                                // ])
                            }
                        },
                        data: [498, 520, 568, 432, 464, 332, 344, 458, 470, 468, 398, 310, 421],
                        z: 10,
                        zlevel: 0
                    },
                    {
                        // 分隔
                        type: "pictorialBar",
                        itemStyle: {
                            normal: {
                                color: "#0F375F"
                            }
                        },
                        symbolRepeat: "fixed",
                        symbolMargin: 6,
                        symbol: "rect",
                        symbolClip: true,
                        symbolSize: [18, 2],
                        symbolPosition: "start",
                        symbolOffset: [1, 1],
                        data: [498, 520, 568, 432, 464, 332, 344, 458, 470, 468, 398, 310, 421],
                        width: 2,
                        z: 0,
                        zlevel: 1
                    },
                    {
                        name: "外框",
                        type: "bar",
                        barGap: "-110%", // 设置外框粗细
                        data: [100, 100, 100, 100, 100, 100, 100],
                        barWidth: 16,
                        itemStyle: {
                            normal: {
                                color: "transparent", // 填充色
                                // barBorderRadius: 0, //圆角半径
                                label: {
                                    // 标签显示位置
                                    show: false,
                                    position: "top" // insideTop 或者横向的 insideLeft
                                }
                            }
                        },
                        z: 0
                    },
                    {
                        name: "背影",
                        type: "line",
                        smooth: true, //平滑曲线显示
                        showAllSymbol: false, //显示所有图形。
                        symbolSize: 0,
                        lineStyle: {
                            width: 0
                        },
                        areaStyle: {
                            color: "rgba(0, 151, 251, 0.1)"
                        },
                        data: [498, 520, 568, 432, 464, 332, 344, 458, 470, 468, 398, 310, 421],
                        z: 5
                    }
                ],
                // dataZoom: [
                //   {
                //     type: "slider",
                //     show: false,
                //     xAxisIndex: [0],
                //     endValue: 14,
                //     startValue: 0
                //   }
                // ]
            })
        },
        egtjdtChart() {
            let jdtChart = this.$echarts.init(document.getElementById("jdtChart"));
            let xData = [30]
            let yData = [100]
            jdtChart.setOption({

                grid: {
                    top: 0,
                    bottom: 0,
                    left: '10%',
                    right: '10%',
                },
                xAxis: {
                    show: false,
                    type: 'value',
                    boundaryGap: [0, 0],
                },
                yAxis: [
                    {
                        type: 'category',
                        data: [''],
                        axisLine: { show: false },
                        axisTick: [
                            {
                                show: false,
                            },
                        ],
                    },
                ],
                series: [
                    {
                        name: '金额',
                        type: 'bar',
                        zlevel: 1,
                        itemStyle: {
                            normal: {
                                barBorderRadius: 30,
                                color: this.$echarts.graphic.LinearGradient(1, 0, 0, 1, [
                                    {
                                        offset: 1,
                                        color: 'rgb(146, 208, 80)',
                                    },
                                    {
                                        offset: 0,
                                        color: 'rgb(146, 208, 80)',
                                    },
                                ]),
                            },
                        },
                        barWidth: 20,
                        data: xData,

                    },
                    {
                        name: '背景',
                        type: 'bar',
                        barWidth: 20,
                        barGap: '-100%',
                        data: yData,
                        itemStyle: {
                            normal: {
                                color: 'rgb(68, 114, 196)',
                                borderWidth: 1,
                                borderColor: '#f84f2e20',
                                barBorderRadius: 30,
                            },
                        },
                        label: {
                            show: true,
                            verticalAlign: "middle",
                            position: ['70%', '-80%'],
                            fontSize: 40,
                            color: 'rgb(132, 190, 72)',
                            formatter: function (data) {
                                return xData[0] + "%";
                            }
                        },
                    },
                ],
            })
        },
        resizeChart() {

            this.getChart()
            this.getChartTop5()
            this.getrkChart()
        }
    },
    beforeDestroy() {
        window.removeEventListener('resize', this.resizeChart);

    },
    mounted() {
        this.getChart();
        this.getChartTop5();
        this.getrkChart()
        this.getkcwzChart()
        this.egtjdtChart()
        window.addEventListener('resize', this.resizeChart);
    },
}
</script>
<style scoped lang="scss">
.home {
    display: flex;
    flex-direction: column;
    align-items: center;
    width: 100%;
    height: 100%;

    .home-tb {
        color: rgb(255, 255, 255);
        height: 50px;
        width: 100%;
        display: flex;
        justify-content: center;
        position: relative;

        h2 {
            margin-top: 8px;
        }

        .time {
            position: absolute;
            left: 20px;
            top: 8px;
            display: flex;

            .yaer-box {
                display: flex;
                align-items: center;
                justify-content: center;

                select {
                    border: none;
                    margin-left: 5px;
                }
            }

            .yuefen {
                margin-left: 20px;

                select {
                    border: none;
                    margin-left: 5px;
                }
            }

            .btn {
                padding: 0 8px;
                border-radius: 3px;
                background-color: rgb(75, 150, 243);
                font-size: 10px;
                display: flex;
                justify-content: center;
                align-items: center;
                margin-left: 30px;
            }

        }
    }

    .home-db {
        display: flex;

        height: 100%;
        width: 100%;

        .home-left {
            width: 25%;
            height: 100%;
            display: flex;
            flex-direction: column;
            padding: 0 5px;
            box-sizing: border-box;

            .home-left1 {
                width: 100%;
                height: 20%;
                padding: 10px;
                box-sizing: border-box;
                display: flex;

                .zb {
                    flex: 1;

                    .sb {
                        display: flex;

                        .ddzl {
                            font-size: 15px;
                            padding: 2px 6px;
                            background-color: rgb(237, 125, 49);
                            border-radius: 4px;
                            color: #fff;
                            margin-left: 10px;
                        }
                    }

                    .xb {
                        display: flex;
                        justify-content: end;
                        font-size: 35px;
                        padding-right: 20px;
                        color: #fff;
                        padding-top: 10px;
                        font-weight: bold;
                    }
                }

                .yb {
                    flex: 1;

                }
            }

            .home-left2 {
                width: 100%;
                height: 43%;

            }

            .home-left3 {
                width: 100%;
                height: 32%;
                margin-top: 5px;
                margin-bottom: 5px;
            }
        }

        .home-mid {
            width: 50%;

            // background: url(../../assets/mid-bg.png);
            // background-repeat: no-repeat;
            // background-size: 100% 80%;
            // z-index: 99;
            background-color: transparent;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            color: #fff;

            box-sizing: border-box;

            .home-mid-tb {
                width: 100%;
                height: 8%;
                display: flex;
                align-items: center;

                .gcsxl {
                    font-size: 20px;
                    margin-left: 10px;

                }
            }

            .home-mid-zm {
                height: 80%;
                background: url(../../assets/mid-bg.png);
                background-repeat: no-repeat;
                background-size: 100% 90%;
                position: relative;

                .circle1 {
                    position: absolute;
                    top: 20px;
                    left: 160px;
                    width: 60px;
                    height: 60px;
                    background-color: transparent;
                    background-color: rgba(217, 224, 15, .2);
                    border-radius: 50%;
                    
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                    align-items: center;

                    /* 确保内部阴影不会溢出 */
                    .line {
                        width: 1px;
                        height: 60px;
                        background-color: rgb(110, 112, 46);
                        position: absolute;
                        bottom: -60px;
                    }

                    .nc {
                        color: #fff;
                        font-size: 16px;
                    }

                    .num {
                        font-size: 12px;
                    }
                }
                .circle2 {
                    position: absolute;
                    top: -20px;
                    left: 260px;
                    width: 90px;
                    height: 90px;
                    background-color: transparent;
                    background-color: rgba(96, 61, 23,.7);
                    border-radius: 50%;
                    
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                    align-items: center;

                    /* 确保内部阴影不会溢出 */
                    .line {
                        width: 1px;
                        height: 60px;
                        background-color: rgb(96, 61, 23);
                        position: absolute;
                        bottom: -60px;
                    }

                    .nc {
                        color: #fff;
                        font-size: 20px;
                       
                    }

                    .num {
                       
                        font-size: 16px;
                    }
                }
                .circle3 {
                    position: absolute;
                    top: 50px;
                    left: 380px;
                    width: 50px;
                    height: 50px;
                    background-color: transparent;
                    background-color: rgba(6, 101, 68,.7);
                    border-radius: 50%;
                    
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                    align-items: center;

                    /* 确保内部阴影不会溢出 */
                    .line {
                        width: 1px;
                        height: 60px;
                        background-color: rgb(6, 101, 68);
                        position: absolute;
                        bottom: -60px;
                    }

                    .nc {
                        color: #fff;
                        font-size: 12px;
                    
                    }

                    .num {
                       
                        font-size: 12px;
                    }
                }
                .circle4 {
                    position: absolute;
                    top: -25px;
                    right: 200px;
                    width: 110px;
                    height: 110px;
                    background-color: transparent;
                    background-color: rgba(94, 41, 116,.7);
                    border-radius: 50%;
                    
                    display: flex;
                    flex-direction: column;
                    justify-content: center;
                    align-items: center;

                    /* 确保内部阴影不会溢出 */
                    .line {
                        width: 1px;
                        height: 90px;
                        background-color: rgb(94, 41, 116);
                        position: absolute;
                        bottom: -90px;
                    }

                    .nc {
                        color: #fff;
                        font-size: 22px;
                    
                    }

                    .num {
                       
                        font-size: 16px;
                    }
                }


            }

            .home-mid-db {
                height: 35%;

                .kcxx-box {
                    display: flex;
                    height: 30px;
                    align-items: center;
                    margin-left: 30px;

                    .kcxx {
                        font-size: 20px;
                        margin-left: 10px;
                    }

                }

                .bfb-box {
                    display: flex;
                    justify-content: flex-start;
                    flex-wrap: wrap;
                    padding: 10px 40px;
                    height: 68%;

                    .bfb-item {
                        margin-right: 40px;
                        width: calc((100% - 80px) / 3);
                        display: flex;
                        justify-content: center;
                        align-items: center;
                        flex-direction: column;
                        height: 100%;
                        border-radius: 5px;

                        .tt {}

                        .bl1 {
                            font-size: 30px;
                            color: rgb(60, 224, 238);
                            font-weight: bold;
                        }

                        .bl2 {
                            font-size: 30px;
                            color: rgb(103, 59, 229);
                            font-weight: bold;

                        }

                        .bl3 {
                            font-size: 30px;
                            color: rgb(255, 164, 23);
                            font-weight: bold;
                        }

                        .yyl {
                            font-size: 14px;
                        }

                    }

                    .bfb-item:nth-child(3n) {
                        margin-right: 0;
                    }

                    .bft1 {
                        border: 1px solid rgb(37, 145, 154);

                    }

                    .bft2 {
                        border: 1px solid rgb(103, 59, 229);
                    }

                    .bft3 {
                        border: 1px solid rgb(238, 162, 23);
                    }
                }
            }

        }

        .home-right {
            width: 25%;
            height: 100%;

            .home-left1 {
                width: 100%;
                height: 20%;
                padding: 10px 0;
                box-sizing: border-box;
                display: flex;
                flex-direction: column;

                .qxxs {
                    display: flex;
                    align-items: center;
                    height: 30px;

                    .qxxs-text {
                        font-size: 20px;
                        margin-left: 10px;
                        color: #fff;
                    }

                }

                .wsgxs-box {
                    display: flex;
                    justify-content: end;
                    align-items: center;

                    .wsgxs-left {
                        color: #fff;
                        display: flex;
                        flex-direction: column;
                        font-size: 12px;
                        margin-right: 30px;
                    }

                    .wsgxs-right {
                        display: flex;
                        align-items: center;
                        margin-right: 30px;

                        .ts {
                            font-size: 30px;
                            color: rgb(132, 190, 78);
                            font-weight: bold;
                        }

                        .tian {
                            color: rgb(48, 96, 154);
                        }
                    }
                }

            }

            .home-left2 {
                width: 100%;
                height: 43%;

            }

            .home-left3 {
                width: 100%;
                height: 32%;
                margin-top: 5px;
                margin-bottom: 5px;
            }

        }
    }

}
</style>