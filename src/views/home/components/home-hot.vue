<template lang="">
  <div class="home-hot">
    <homePanel title="新鲜好物" sub-title="人气爆款 不容错过">
      <div ref="target"  style="position:relative;height:426px">
        <ul class="goods-list">
          <li v-for="item in goods" :key="item.id">
            <RouterLink to="/">
              <img :src="item.picture" alt="" />
              <p class="name">{{ item.title }}</p>
              <p class="desc">{{ item.alt }}</p>
            </RouterLink>
          </li>
        </ul>
      </div>
    </homePanel>
  </div>
</template>
<script>
import { findHot } from '@/api/home'
import homePanel from './home-panel.vue'
import { useLazyData } from '../../../hooks'

export default {
  name: 'HomeHot',
  components: {
    homePanel
  },
  setup () {
    const { target, result } = useLazyData(findHot)

    // findHot().then((data) => {
    //   goods.value = data.result;
    //   //   console.log(list.value)
    // });
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
  height: 426px;
  li {
    width: 306px;
    height: 406px;
    .hoverShadow();
    img {
      width: 306px;
      height: 306px;
    }
    p {
      font-size: 22px;
      padding-top: 12px;
      text-align: center;
    }
    .desc {
      color: #999;
      font-size: 18px;
    }
  }
}
</style>
