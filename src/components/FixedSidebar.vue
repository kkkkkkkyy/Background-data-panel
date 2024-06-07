<template>
    <div class="sidebar-container">
        <div class="sidebar">
            <h3 style="font-size: 20px">后台数据看板</h3>
            <!-- 侧边栏内容 -->
            <ul>
                <li v-for="(item, index) in menuItems" :key="index">
                    <span :class="{ 'active': index === activeIndex }" @click="activate(index)">
                        <a @click.prevent>
                            {{ item.text }}
                        </a>
                    </span>
                </li>
            </ul>
        </div>
    </div>
</template>

<script>
export default {
    name: 'FixedSidebar',
    data() {
        return {
            activeIndex: 0,
            menuItems: [
                { href: '#SectionOne', text: '数据分析', component: 'SectionOne' },
                { href: '#SectionTwo', text: '词库管理', component: 'SectionTwo' },
                { href: '#XXXXXXX', text: '功能模块', component: 'XXXXXXX' },
                { href: '#XXXXXXX', text: '模型性能', component: 'XXXXXXX' },
                { href: '#XXXXXXX', text: '用户反馈', component: 'XXXXXXX' },
            ],
        }
    },
    methods: {
        activate(index) {
            this.activeIndex = index;
            this.$emit('change-component', this.menuItems[index].component); // 通知父组件更改当前组件
        }
    }
}
</script>



<style scoped>
.sidebar-container {
    text-align: center;
    position: fixed;
    left: 0;
    top: 0;
    height: 100%;
    width: 180px;
    background-color: #f8f9fa;
    z-index: 1000;
}

.sidebar {
    padding-top: 25px;
}

ul {
    list-style-type: none;
    padding: 0;
}

li {
    font-size: 14px;
    margin-bottom: 15px;
}

a {
    cursor: pointer;
    display: block;
    padding: 10px;
    margin-left: 10px;
    margin-right: 10px;
    border-radius: 8px;
    text-decoration: none;
    color: #333;
    transition: background-color 0.3s, color 0.3s;
}

a:hover,
.active a {
    background-color: #dee2e6;
}

.active a {
    color: #ffffff;
    background-color: #00ce8b;
}

/* 防止.active样式影响悬停效果 */
.active:hover a {
    background-color: #00ce8b;
}
</style>
