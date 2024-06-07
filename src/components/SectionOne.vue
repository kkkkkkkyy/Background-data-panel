<template>
    <div id="SectionOne">
        <!-- part1 -->
        <div class="flex-container">
            <div class="flex-item-1">
                <echart1 />
            </div>
            <div class="flex-item-2">
                <echart4 />
            </div>
        </div>
        <!--  -->
        <div class="gender_echart">
            <!-- part3 -->
            <div class="container">
                <div class="info-box">
                    <p>第一使用地域:</p>
                    <p><span style="font-size: 24px">广东</span></p>
                </div>
                <div class="info-box">
                    <p>平均加载时间：</p>
                    <p><span style="font-size: 24px">3</span>分钟</p>
                </div>
                <div class="info-box">
                    <p>平均用户年龄：</p>
                    <p><span style="font-size: 24px">26</span>岁</p>
                </div>
            </div>
            <!-- part2 -->
            <h3 style="display: block;">用户性别比例:</h3>
            <div class="gender_chart">
                <p style="padding: 10px;">四月</p>
                <GenderOne />
            </div>
            <div class="gender_chart">
                <p style="padding: 10px;">五月</p>
                <GenderTwo />
            </div>
            <div class="gender_chart">
                <p style="padding: 10px;">六月</p>
                <GenderThree />
            </div>
        </div>

    </div>
</template>

<script>
import echart1 from './ECharts/echart1.vue';
import echart4 from './ECharts/echart4.vue';
import GenderOne from './ECharts/gender/GenderOne.vue';
import GenderTwo from './ECharts/gender/GenderTwo.vue';
import GenderThree from './ECharts/gender/GenderThree.vue';
export default {
    name: 'SectionOne',
    components: {
        echart1,
        echart4,
        GenderOne,
        GenderTwo,
        GenderThree
    },
}
</script>
<!-- All -->
<style scoped>
#SectionOne {
    padding-left: 200px;
}


/* part1 */
.flex-container {
    display: flex;
    justify-content: space-between;
}

.flex-item-1 {
    width: 65%;
    margin-right: 10px;
}

.flex-item-2 {
    width: 35%;
}


/* part2 */
.gender_echart {
    display: flex;
    justify-content: space-around;
}

.gender_chart {
    width: 22%;
}



/* part3 */
.container {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin: 0px 70px 0px 25px;
}

.info-box {
    width: 180px;
    background-color: white;
    border-radius: 10px;
    padding: 20px;
    box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
    margin-bottom: 15px;
}

p {
    margin: 0;
    font-size: 15px;
}
</style>
