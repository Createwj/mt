<template>
  <el-container class="layout-default">
    <el-header height="197px">
      <my-header/>
    </el-header>
    <el-main style="overflow: initial;margin: 0 auto">
      <nuxt/>
    </el-main>
    <el-footer height="100%">
      <footers></footers>
    </el-footer>
  </el-container>
</template>
<script>
  import MyHeader from '@/components/public/header/index.vue'
  import Footers from '@/components/public/footer/index.vue'
  export default {
    components:{
      MyHeader,
      Footers
    }
  }
</script>
<style>
  html,body{
    background: #fff;
  }
</style>
