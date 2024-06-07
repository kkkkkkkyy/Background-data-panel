<template>
    <div id="SectionTwo">
        <h1>我是SectionTwo</h1>
        <p>我可以做词库管理,在这里写代码</p>
    </div>
</template>

<script>
export default {
    name: 'SectionTwo',
    data() {
        return {
        }
    },
    mounted() {
    },
    methods: {
    }
}
</script>

<style scoped>
#SectionTwo {
    /* 避免被侧边栏覆盖 */
    padding-left: 200px;
}
</style>