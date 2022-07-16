<template lang="">
    <div>
        <!-- 顶部 -->
        <AppNavbar></AppNavbar>
        <!-- 头部 -->
        <AppHeader></AppHeader>
        <!-- 吸顶头部 -->
        <AppHeaderSticky></AppHeaderSticky>
        <div class="app-body">
            <router-view></router-view>
        </div>
        <AppFooter></AppFooter>
    </div>
</template>
<script>
import AppNavbar from '@/components/app-navbar'
import AppHeader from '@/components/app-header'
import AppFooter from '@/components/app-footer'
import AppHeaderSticky from '../components/app-header-sticky.vue'
import { useStore } from 'vuex'
export default {
  components: {
    AppNavbar,
    AppHeader,
    AppFooter,
    AppHeaderSticky
  },
  setup () {
    const store = useStore()
    store.dispatch('category/getList')
  }
}
</script>
<style lang="less" scoped>
.app-body{
    min-height: 600px;
}
</style>
