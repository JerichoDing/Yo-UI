<template>
  <div class="layout" :class="layoutClass">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: "GuluLayout",
    data(){
      return{
        layoutClass:{
          hasSider:false
        }
      }
    },
    mounted(){
      this.$children.forEach(vm =>{
        if (vm.$options.name ==='GuluSider'){
          this.layoutClass.hasSider = true
        }
      })
    },
  }
</script>

<style scoped lang="scss">
  .layout{
    display: flex;
    flex-direction: column;
    border: 1px solid red;
    min-height: 100px;
    flex-grow: 1;
  }
  .hasSider{
    flex-direction: row;
  }
</style>
