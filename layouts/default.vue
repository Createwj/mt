<template>
  <el-container class="layout-default">
    <el-header height="197px">
      <my-header/>
    </el-header>
    <el-main style="overflow: initial;width: 1190px;margin: 0 auto">
      <nuxt/>
    </el-main>
    <el-footer height="100%">Footer</el-footer>
  </el-container>
</template>
<script>
  import MyHeader from '@/components/public/header/index.vue'
  export default {
    components:{
      MyHeader
    }
  }
</script>
<style>
  html,body{
    background: #efefef;
  }
</style>
