<template>
    <div>
        <h3>新老用户留存情况</h3>
        <div style="width: auto;height: 390px" id="echartsFour">
        </div>
    </div>
</template>

<script>
import echarts from 'echarts'

export default {
    name: 'echartsFour',
    data() {
        return {
            option: {
                color: ['#003366', '#006699', '#4cabce', '#e5323e'],
                tooltip: {
                    trigger: 'axis',
                    axisPointer: {
                        type: 'shadow'
                    }
                },
                legend: {
                    data: ['新用户留存', '老用户留存']
                },
                xAxis: [
                    {
                        type: 'category',
                        axisTick: { show: false },
                        data: ['四月', '五月', '六月']
                    }
                ],
                yAxis: [
                    {
                        type: 'value'
                    }
                ],
                series: [
                    {
                        name: '新用户留存',
                        type: 'bar',
                        label: {
                            show: true,
                            position: 'top',
                            distance: 15,
                            align: 'left',
                            verticalAlign: 'middle',
                            rotate: 90,
                            formatter: '{c}人',
                            fontSize: 16,
                            rich: {
                                name: {
                                    textBorderColor: '#fff'
                                }
                            }
                        },
                        data: [45, 48, 50]
                    },
                    {
                        name: '老用户留存',
                        type: 'bar',
                        label: {
                            show: true,
                            position: 'top',
                            distance: 15,
                            align: 'left',
                            verticalAlign: 'middle',
                            rotate: 90,
                            formatter: '{c}人',
                            fontSize: 16,
                            rich: {
                                name: {
                                    textBorderColor: '#fff'
                                }
                            }
                        },
                        data: [27, 35, 62]
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
            echarts.init(document.getElementById('echartsFour')).setOption(this.option)
        }
    }
}
</script>

<style scoped>
</style>
