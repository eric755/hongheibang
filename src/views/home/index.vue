<template>
  <el-container>
    <el-header>
      <top />
    </el-header>
    <menu-list />
    <el-container>
      <main-left />
      <main-right />
    </el-container>
    <foot />
  </el-container>
</template>

<script>
import Top from '@/components/top'
import MenuList from '@/components/menu_list'
import MainLeft from '@/components/main_left'
import MainRight from '@/components/main_right'
import Foot from '@/components/foot'
export default {
  name: 'home',
  data () {
    return {}
  },
  components: {
    Top,
    MenuList,
    MainLeft,
    MainRight,
    Foot
  }
}
</script>

<style lang="less" scoped>
.home {
  height: 100%;
}
.el-header,
.el-footer {
  height: auto !important;
  background-color: #252932;
  color: #333;
  text-align: center;
  line-height: 60px;
}
.el-header {
  background-color: #0777dd;
}
.el-aside {
  background-color: #d3dce6;
  color: #333;
  text-align: center;
  line-height: 200px;
}

.el-main {
  background-color: #e9eef3;
  color: #333;
  text-align: center;
  line-height: 160px;
}

body > .el-container {
  margin-bottom: 0px;
}

.el-container:nth-child(5) .el-aside,
.el-container:nth-child(6) .el-aside {
  line-height: 260px;
}

.el-container:nth-child(7) .el-aside {
  line-height: 320px;
}
</style>
