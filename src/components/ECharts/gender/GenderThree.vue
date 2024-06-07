<template>
    <div id="GenderThree">
        <echarts :option="option" />
    </div>
</template>

<script>
import echarts from 'echarts'

export default {
    name: 'GenderThree',
    data() {
        return {
            option: {
                tooltip: {
                    trigger: 'item',
                    formatter: '{a} <br/>{b} : {c} ({d}%)'
                },
                legend: {
                    orient: 'vertical',
                    left: 'left',
                    data: ['男', '女']
                },
                series: [
                    {
                        name: '六月性别比例',
                        type: 'pie',
                        radius: '55%',
                        center: ['50%', '50%'],
                        data: [
                            { value: 1.8, name: '男' },
                            { value: 1, name: '女' }
                        ],
                        emphasis: {
                            itemStyle: {
                                shadowBlur: 10,
                                shadowOffsetX: 0,
                                shadowColor: 'rgba(0, 0, 0, 0.5)'
                            }
                        }
                    }
                ]
            }
        }
    },
    mounted() {
        this.initChart()
    },
    methods: {
        initChart() {
            const myChart = echarts.init(document.querySelector('#GenderThree'))
            myChart.setOption(this.option)
        }
    }
}
</script>

<style scoped>
#GenderThree {
    width: 100%;
    height: 350px;
}
</style>