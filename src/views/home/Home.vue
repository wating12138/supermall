<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :banners="banners"/>
    <recommend-view :recommends="recommends"/>
  </div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar";
  import HomeSwiper from "./childComps/HomeSwiper";
  import {getHomeMultidata} from "network/home";
  import RecommendView from "./childComps/RecommendView";

  export default {
    name: "Home",
    components: {
      NavBar,
      HomeSwiper,
      RecommendView
    },
    data() {
      return {
        banners: [],
        dkeywords: [],
        keywords: [],
        recommends: []
      }
    },
    created() {
      getHomeMultidata().then(
        res => {
          console.log(res);
          this.banners = res.data.banner.list;
          this.dkeywords = res.data.dkeyword;
          this.keywords = res.data.keyword;
          this.recommends = res.data.recommend.list;
        })
    }
  }
</script>

<style scoped>
  .home-nav {
    background-color: var(--color-tint);
    color: #fff;
  }
</style>
