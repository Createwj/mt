<template>
  <div class="m-menu">
    <dl class="nav" @mouseleave="mouseleave">
      <dt>全部分类</dt>
      <dd v-for="(item,ids) in emenu" :key="ids" @mouseenter="mouseenter">
        <i :class="item.type"/>{{item.name}} <span class="arrow"/>
      </dd>
    </dl>
    <!-- 鼠标hover之后显示相对应的子菜单 -->
    <div class="detail" v-if="kind" @mouseleave="leaves" @mouseenter="enters">

     <template v-for="(item,idx) in curdetail.child">
        <h4 :key="idx">{{item.title}}</h4>
        <span v-for="v in item.child">{{v}}</span>

     </template>
    </div>
  </div>
</template>

<script>
  export default {
    name: "emenu",
    data(){
      return{
        kind:'',
        emenu:[{
          type:'food',
          name:'美食',
          child:[{
            title:'meishi',
            child:['代金劵','代金劵','代金劵']
          },
          {
            title:'meishi',
            child:['代金劵','代金劵','代金劵']
          }]
        },
        {
          type:'takeout',
          name:'外卖',
           child:[{
            title:'e',
            child:['1','3','2']
          }]
        },{
          type:'hotel',
          name:'酒店',
          child:[{
            title:'q',
            child:['q','w','e']
          }]
          }]
      }
    },
    computed:{
      // 根据计算属性 显示子菜单
      curdetail:function(){
        return this.emenu.filter((item)=>item.type===this.kind)[0]
      }
    },
    methods:{
      mouseleave(){
        let that = this
        that._time = setTimeout(()=>{
          that.kind = ''
        },150)
      },
      mouseenter(e){
        this.kind=e.target.querySelector('i').className
      },
      enters(){
        clearTimeout(this._time)
      },
      leaves(){
        this.kind=''
      }
    }
  }
</script>

<style scoped>

</style>
