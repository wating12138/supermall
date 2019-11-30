<template>
  <swiper ref="child">
    <swiper-item v-for="item in banners">
      <a :href="item.link">
        <img :src="item.image" alt="">
      </a>
    </swiper-item>
  </swiper>
</template>

<script>
  import {Swiper, SwiperItem} from 'components/common/swiper'

  export default {
    name: "HomeSwiper",
    components: {
      Swiper,
      SwiperItem
    },
    props: {
      banners: {
        type: Array,
        default() {
          return []
        }
      }
    },
    updated() {
      // 1.操作DOM, 在前后添加Slide
      this.$refs.child.handleDom();

      // 2.开启定时器
      this.$refs.child.startTimer();

      // this.$refs.child.handleDom()
    }
    // created() {
    //   console.log(this.banners);
    // }

  }
</script>

<style scoped>

</style>
