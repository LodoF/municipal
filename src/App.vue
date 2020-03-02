<template>
  <div id="app" class="app-wrapper">
    <!-- 侧边栏 -->
    <el-row class="tac">
      <el-col :span="24" class="head">
        <nav-head class="nav-head"/>
      </el-col>
      <el-col :span="isMobile ? 1 : 4" class="nav">
        <nav-Box class="nav-container"/>
      </el-col>
      <el-col :span="20" class="man">
        <div class="app-main">
          <router-view/>
        </div>
      </el-col>
    </el-row>
  </div>
</template>

<script>
  import navBox from '@/components/navBox'
  import navHead from '@/components/navHead'
  export default {
    name: 'App',
    components: {
      navBox,
      navHead
    },
    data() {
      return {
        isMobile: false,
      }
    },
    created() {
      if(/Android|webOS|iPhone|iPod|BlackBerry/.test(navigator.userAgent)) {
       
      } else {

      }
    }
  }
</script>
<style lang="scss" scoped>

  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    /* margin-top: 60px; */
  }

  .app-wrapper {
    position: relative;
    height: 100%;
    width: 100%;
  }

  .nav-head {
    width: 100%;
    height: 60px;
    background: rgb(84, 92, 100);
    text-align: left;
  }

  .nav-container {
    width: 100%;
    height: 100%;
    text-align: left;
  }

  .app-main {
    width: 100%;
    height: 100%;
  }

  .tac {
    height: 100%;
    .head {
      height: 60px;
    }

    .nav {
      height: calc(100% - 60px);
    }

    .main {
      height: calc(100% - 60px);
    }
  }
</style>
