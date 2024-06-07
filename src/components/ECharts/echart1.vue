<template>
    <div>
        <h3>用户活跃时间</h3>
        <div style="width: auto;height: 350px" id="echartsOne">
        </div>
    </div>
</template>

<script>
import echarts from 'echarts'
export default {
    name: 'echartsOne',
    data() {
        return {
            option: {
                color: ['#ff7f0e', '#1f77b4', '#2ca02c'],
                tooltip: {
                    trigger: 'axis'
                },
                legend: {
                    data: ['三月', '四月', '五月']
                },
                grid: {
                    top: 70,
                    bottom: 50
                },
                xAxis: {
                    type: 'category',
                    boundaryGap: false,
                    data: ['0:00', '2:00', '4:00', '6:00', '8:00', '10:00', '12:00', '14:00', '16:00', '18:00', '20:00', '22:00', '24:00'],
                    axisTick: {
                        alignWithLabel: true
                    }
                },
                yAxis: {
                    type: 'value',
                    min: 0,
                    max: 30,
                    interval: 5
                },
                series: [
                    {
                        name: '三月',
                        type: 'line',
                        data: [0, 0, 0, 0, 0, 1, 4, 2, 8, 3, 3, 0, 0]
                    },
                    {
                        name: '四月',
                        type: 'line',
                        data: [0, 0, 0, 0, 0, 1, 8, 10, 15, 12, 14, 1, 0]
                    },
                    {
                        name: '五月',
                        type: 'line',
                        data: [0, 0, 0, 0, 1, 1, 12, 18, 25, 22, 15, 2, 0]
                    }
                ]
            }
        }
    },
    mounted() {
        this.echartsInit()
    },
    methods: {
        echartsInit() {
            // 在生命周期中挂载
            echarts.init(document.getElementById('echartsOne')).setOption(this.option)
        }
    }
}
</script>

<style scoped></style>