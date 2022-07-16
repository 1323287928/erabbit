<template lang="">
  <div class="home-new">
    <homePanel title="新鲜好物" sub-title="新鲜出品 品质靠谱">
      <template #right><XtxMore path="/"></XtxMore></template>
      <div ref="target"  style="position:relative;height:426px">
      <transition name="fade">
        <ul v-if="goods.length" class="goods-list">
          <li v-for="item in goods" :key="item.id">
            <RouterLink :to="`/product/${item.id}`">
              <img :src="item.picture" alt="" />
              <p class="name ellipsis">{{ item.name }}</p>
              <p class="price">&yen;{{ item.price }}</p>
            </RouterLink>
          </li>
        </ul>
        <homeSkeleton v-else bg="#f0f9f4"></homeSkeleton>
      </transition>
      </div>
    </homePanel>
  </div>
</template>
<script>
import { findNew } from '../../../api/home'
import homePanel from './home-panel.vue'
import homeSkeleton from './home-skeleton.vue'
import { ref } from 'vue'
import { useLazyData } from '@/hooks'
export default {
  name: 'HomeNew',
  components: {
    homePanel,
    homeSkeleton
  },
  setup () {
    // const goods = ref([]);
    // findNew().then((data) => {
    //   goods.value = data.result;
    // });
    // const target=ref(null)
    const { target, result } = useLazyData(findNew)
    return {
      goods: result,
      target
    }
  }
}
</script>
<style lang="less" scoped>

.goods-list {
  display: flex;
  justify-content: space-between;
  height: 406px;
  li {
    width: 306px;
    height: 406px;
    background: #f0f9f4;
    .hoverShadow();
    img {
      width: 306px;
      height: 306px;
    }
    p {
      font-size: 22px;
      padding: 12px 30px 0 30px;
      text-align: center;
    }
    .price {
      color: @priceColor;
    }
  }
}
</style>
