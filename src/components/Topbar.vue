<template>
  <div id="topbar">
    <div class="logo">
      VueResumer
    </div>
    <div class="actions">
      <ElButton type="primary">注册</ElButton>
      <el-button>登录</el-button>
      <el-button v-on:click="preview">预览</el-button>
    </div>
  </div>
</template>

<style lang="scss">
  #topbar{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 16px;
    font-size: 20px;
  }
</style>

<script>
  export default {
    methods:{
      preview(){
        this.$emit('preview')
      }
    }
  }
</script>
