<template>
  <div class="home">
    <el-container>
      <el-aside width="200px">
        <el-menu default-active="1-4-1" class="el-menu-vertical-demo">
          <el-submenu index="1">
            <template slot="title">
              <i class="el-icon-location"></i>
              <span slot="title">导航一</span>
            </template>
            <el-menu-item-group>
              <span slot="title">分组一</span>
              <el-menu-item index="1-1">选项1</el-menu-item>
              <el-menu-item index="1-2">选项2</el-menu-item>
            </el-menu-item-group>
            <el-menu-item-group title="分组2">
              <el-menu-item index="1-3">选项3</el-menu-item>
            </el-menu-item-group>
            <el-submenu index="1-4">
              <span slot="title">选项4</span>
              <el-menu-item index="1-4-1">选项1</el-menu-item>
            </el-submenu>
          </el-submenu>
          <el-menu-item index="2">
            <i class="el-icon-menu"></i>
            <span slot="title">导航二</span>
          </el-menu-item>
          <el-menu-item index="3" disabled>
            <i class="el-icon-document"></i>
            <span slot="title">导航三</span>
          </el-menu-item>
          <el-menu-item index="4">
            <i class="el-icon-setting"></i>
            <span slot="title">导航四</span>
          </el-menu-item>
        </el-menu>
      </el-aside>
      <el-container>
        <el-header class="home-header">Header</el-header>
        <el-main class="home-main">
          <canvas id="hex-canvas" width="5000" height="5000"></canvas>
        </el-main>
        <el-footer>Footer</el-footer>
      </el-container>
    </el-container>
  </div>
</template>

<script>
  import {HexagonGrid} from "../utils/hexagon"

  export default {
    name: 'Home',
    data() {
      return {

      }
    },
    computed: {
      windowWidth() {
        return window.screen.width - 200
      },
      windowHeight() {
        return window.screen.height - 120
      }
    },
    created() {
      this.loadBaidu()
    },
    mounted() {
      this.drawHexagon()
    },
    methods: {
      drawHexagon() {
        let hexagonGrid = new HexagonGrid("hex-canvas", 25);
        hexagonGrid.drawHexGrid(50, 50, 0, 0, true);
        hexagonGrid.drawHexAtColRow(1,12,"#3771bb")
      },
      loadBaidu() {
        this.$post("/test","", "get").then(res => {
          console.log(res);
        }).catch(err => {
          console.log(err);
        })
      }
    }
  }
</script>
<style scoped>
  /*#hex-canvas {*/
  /*width: 3000px;*/
  /*height: 100%;*/
  /*}*/
  .home-header {
    /*height: 1000px !important;*/
  }
  .home-main {
    overflow: scroll;
  }
  #hex-canvas {
    overflow: scroll;
  }
</style>

<style scoped>
  .el-header, .el-footer {
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
  }

  .el-aside {
    background-color: #D3DCE6;
    color: #333;
    text-align: center;
    line-height: 200px;
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

  .el-container:nth-child(5) .el-aside,
  .el-container:nth-child(6) .el-aside {
    line-height: 260px;
  }


  .el-container:nth-child(7) .el-aside {
    line-height: 320px;
  }
</style>
