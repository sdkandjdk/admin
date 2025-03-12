<template>
  <div class="logo">
    <router-link :to="{name:'defaultDocSearch'}">

      <img v-if="navTheme === 'dark'" src="/favicon.ico" alt="logo">
      <img v-else src="/favicon.ico" alt="logo">

      <span v-if="showTitle" class="showTitle">{{ title }}</span>
    </router-link>
  </div>
</template>

<script>
  import { mixin } from '@/utils/mixin.js'

  export default {
    name: 'Logo',
    mixins: [mixin],
    props: {
      title: {
        type: String,
        default: '医学文献库',
        required: false
      },
      showTitle: {
        type: Boolean,
        default: true,
        required: false
      }
    }
  }
</script>
<style lang="less" scoped>

  .showTitle{
    margin-left: 10px;
    font-size: 15px;
    /*color: #303133;*/
    font-weight: 600;
  }



  .sider {
    box-shadow: none !important;
    .logo {

      box-shadow: none !important;
      transition: background 300ms;

      a {
        color: white;
        &:hover {
          color: rgba(255, 255, 255, 0.8);
        }
      }
    }

    &.light .logo {
      background-color: @primary-color;
    }
  }
</style>