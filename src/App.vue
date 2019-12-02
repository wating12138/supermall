<template>
  <div id="app">
    <router-view></router-view>
    <tab-bar/>
  </div>
</template>

<script>
  import tabBar from 'components/content/maintabbar/MainTabBar'

  export default {
    name: 'app',
    components: {
      tabBar
    }
  }
</script>

<style>
  @import "assets/css/base.css";

</style>
