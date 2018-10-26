<template>
  <div class="m-header">
    <el-row>
      <el-col>
        <top-bar/>
      </el-col>
    </el-row>
    <el-row >
      <el-col>
       <searchbar></searchbar>
      </el-col>
    </el-row>
  </div>
</template>

<script>
import topBar from './topbar.vue'
import searchbar from './searchbar.vue'
export default {
  components:{
    topBar,
    searchbar
  }
}
</script>

<style lang="scss">
  @import "@/assets/css/public/header/index.scss";
</style>
