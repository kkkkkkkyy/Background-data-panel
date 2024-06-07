<template>
  <div id="app">
    <!-- 左侧：导航菜单栏 -->
    <FixedSidebar @change-component="changeComponent"></FixedSidebar>
    <!-- 右侧：内容 -->
    <component :is="currentComponent"></component>
  </div>
</template>

<script>
import FixedSidebar from './components/FixedSidebar.vue'
import SectionOne from './components/SectionOne.vue'
import SectionTwo from './components/SectionTwo.vue'

export default {
  name: 'App',
  components: {
    FixedSidebar,
    SectionOne,
    SectionTwo
  },
  data() {
    return {
      currentComponent: 'SectionOne' // 默认展示Section1
    }
  },
  methods: {
    changeComponent(componentName) {
      this.currentComponent = componentName; // 根据传递的组件名来切换组件
    }
  }
}
</script>

<style>

</style>