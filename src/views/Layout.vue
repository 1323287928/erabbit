<template lang="">
    <div>
        <!-- 顶部 -->
        <AppNavbar></AppNavbar>
        <!-- 头部 -->
        <AppHeader></AppHeader>
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
export default {
  components: {
    AppNavbar,
    AppHeader,
    AppFooter
  }
}
</script>
<style lang="less" scoped>
.app-body{
    min-height: 600px;
}
</style>
