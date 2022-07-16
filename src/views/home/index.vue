<template lang="">
    <div class="home-entry">
        <div class="container">
            <homeCategory></homeCategory>
            <HomeBanner></HomeBanner>
        </div>
    </div>
    <homeNew></homeNew>
    <homeHot></homeHot>
    <homeBrand></homeBrand>
    <homeProduct></homeProduct>
    <homeSpecial></homeSpecial>
</template>
<script>
import homeCategory from './components/home-category.vue'
import HomeBanner from './components/home-banner.vue'
import homeNew from './components/home-new.vue'
import homeHot from './components/home-hot.vue'
import homeBrand from './components/home-brand.vue'
import homeProduct from './components/home-product.vue'
import homeSpecial from './components/home-special.vue'
export default {
  name: 'HomePage',
  components: {
    homeCategory,
    HomeBanner,
    homeNew,
    homeHot,
    homeBrand,
    homeProduct,
    homeSpecial
  }
}
</script>

<style lang="less" scoped>
.container{
   .hoverShadow ();
   color:@xtxColor;
}
</style>
