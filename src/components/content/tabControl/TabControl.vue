<template>
  <div class="tab-control">
    <div v-for="(item,index) in titles"
         class="tab-control-item" :class="{active:index === currentIndex}"
         @click="ItemClick(index)">
      <span>{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "TabControl",
  props:{
    titles:{
      type:Array,
      default(){
        return []
      }
    }
  },
  data(){
    return{
      currentIndex:0
    }
  },
  methods:{
    ItemClick(index){
      this.currentIndex = index
    }
  }
}
</script>

<style scoped>
.tab-control{
  display: flex;
  text-align: center;
  font-size: 16px;
  height: 40px;
  line-height: 40px;
}
.tab-control-item{
  flex: 1;
}
.tab-control-item span{
  padding: 8px;
}
.active{
  color: var(--color-high-text);
}
.active span{
  border-bottom: 3px solid var(--color-tint);
}
</style>
