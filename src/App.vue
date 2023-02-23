<template>
  <el-container>
    <el-header>
      <el-row class="row1">
        <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
          <el-menu-item index="1"><router-link to="/">Home</router-link></el-menu-item>
          <el-submenu index="2">
            <template slot="title"><router-link to="/about">What We Do</router-link></template>
            <el-menu-item index="2-1">选项1</el-menu-item>
            <el-menu-item index="2-2">选项2</el-menu-item>
            <el-menu-item index="2-3">选项3</el-menu-item>
          </el-submenu> 
          <el-submenu index="3">
            <template slot="title"><router-link to="/test">Why We Exist</router-link> </template>
            <el-menu-item index="3-1">选项1</el-menu-item>
            <el-menu-item index="3-2">选项2</el-menu-item>
            <el-menu-item index="3-3">选项3</el-menu-item>
          </el-submenu> 
          <el-button type="primary" id="button1">主要按钮</el-button>
        </el-menu>
      </el-row>
    </el-header>
    <el-main>
      <router-view></router-view>
    </el-main>
    <el-footer>Footer</el-footer>
  </el-container>  
</template>

<script>
import { RouterView } from 'vue-router';

export default {
  data() {
      return {
          activeIndex: "1"
      };
  },
  methods: {
      handleSelect(key, keyPath) {
          console.log(key, keyPath);
      }
  },
  components: { RouterView },
};
</script>

<style>
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    line-height: 60px;
  }
  .el-header{
    background-color: white;
  }
  .el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    line-height: 160px;
  }
  body > .el-container {
    margin-bottom: 40px;
  }
  .el-menu-item{
    font-size: large;;
  }
</style>