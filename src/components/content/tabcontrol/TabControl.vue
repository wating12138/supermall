<template>
  <div class="tab-control">
    <div v-for="(item,index) in text" @click="itemClick(index)"
         class="tab-control-item"
         :class="{active:index===currentIndex}"><span>{{item}}</span></div>
  </div>
</template>

<script>
  export default {
    name: "TabControl",
    data() {
      return {
        currentIndex: 0
      }
    },
    props: {
      text: {
        type: Array,
        default() {
          return [];
        }
      }
    }, methods: {
      itemClick(index) {
        this.currentIndex = index;
      }
    }
  }
</script>

<style scoped>
  .tab-control {
    display: flex;
    text-align: center;
    height: 40px;
    line-height: 40px;
    font-size: 15px;
    background-color: #fff;
  }

  .tab-control-item {
    flex: 1;
  }

  .active {
    color: var(--color-high-text);
  }

  .active span {
    border-bottom: 3px solid var(--color-tint);
    padding-bottom: 5px;
  }
</style>
