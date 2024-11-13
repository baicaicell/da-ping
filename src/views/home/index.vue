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
                <Card title="出库排名TOP5">
                    333
                </Card>
            </div>
            <div class="home-mid">
                12
            </div>
            <div class="home-right">3</div>
        </div>

    </div>
</template>

<script>
import Card from '@/components/Card.vue'
export default {
    name: 'HelloWorld',
    components: {
        Card
    },
    data() {
        return {
            yaerValue: '',
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
            width: 20%;
            height: 100%;

        }

        .home-mid {
            width: 60%;
            margin-top: 80px;
            background: url(../../assets/mid-bg.png);
            background-repeat: no-repeat;
            background-size: 100% 80%;
            // z-index: 99;
            background-color: transparent;
        }

        .home-right {
            width: 20%;
            height: 100%;

        }
    }

}
</style>