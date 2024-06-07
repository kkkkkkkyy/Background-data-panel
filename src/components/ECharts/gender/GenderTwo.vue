<template>
    <div id="GenderTwo">
        <echarts :option="option" />
    </div>
</template>

<script>
import echarts from 'echarts'

export default {
    name: 'GenderTwo',
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
                        name: '五月性别比例',
                        type: 'pie',
                        radius: '55%',
                        center: ['50%', '50%'],
                        data: [
                            { value: 2, name: '男' },
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
            const myChart = echarts.init(document.querySelector('#GenderTwo'))
            myChart.setOption(this.option)
        }
    }
}
</script>

<style scoped>
#GenderTwo {
    width: 100%;
    height: 350px;
}
</style>