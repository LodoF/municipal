<template>
  <div>
    <el-menu class="el-menu-vertical-demo" background-color="#545c64" text-color="#fff" active-text-color="#ffd04b" :router="true">
      <el-submenu  v-for="nav in navList" :key="nav.index" :index="nav.index">
        <template slot="title">
          <i :class="nav.icon"></i>
          <span>{{nav.title}}</span>
        </template>
        <el-menu-item v-for="nav_child in nav.children" :key="nav_child.index" :index="nav_child.index">
          <i :class="nav_child.icon"></i>
          {{nav_child.title}}
        </el-menu-item>
      </el-submenu>
    </el-menu>
  </div>
</template>
<script>
  export default {
    name: 'navBox',
    data() {
      return {
        navList: [
          {
            index: '/',
            title: '首页',
            icon: 'el-icon-menu',
            children: [
              {
                index: '/test',
                title: '测试',
                icon: 'el-icon-school',
              },
              {
                index: '/test2',
                title: '测试2',
                icon: 'el-icon-house',
              }
            ]
          },
          {
            index: '/index2',
            title: '测试导航2',
            icon: 'el-icon-menu',
            children: [
              {
                index: '/test22',
                title: '测试',
                icon: 'el-icon-office-building',
              },
              {
                index: '/test233',
                title: '测试2',
                icon: 'el-icon-school',
              }
            ]
          }
        ]
      }
    },
    methods: {

    },
    created() {

    }
  }
</script>
<style lang="scss" scoped>
  .el-menu-vertical-demo {
    height: 100%;
  }
</style>