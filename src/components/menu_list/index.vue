<template>
  <el-menu
    :default-active="activeIndex"
    class="el-menu-demo"
    mode="horizontal"
    @select="handleSelect"
  >
    <el-menu-item index="1">首页</el-menu-item>
    <el-menu-item index="2">红黑榜</el-menu-item>
    <el-menu-item index="3">汽车投诉</el-menu-item>
    <el-menu-item index="4">信息资讯</el-menu-item>
    <el-menu-item index="5">缺陷召回</el-menu-item>
    <el-menu-item index="6">投诉排行</el-menu-item>
    <el-menu-item index="7">分析报告</el-menu-item>
    <el-menu-item index="8">协作媒体</el-menu-item>

    <el-button class="complaint_bt" type="danger" @click="dialogFormVisible = true">
      <i class="el-icon-edit el-icon--right"></i>我要投诉
    </el-button>

    <!-- 登录弹出框 -->
    <el-dialog class="login_window" title="欢迎登录" center :visible.sync="dialogFormVisible">
      <el-form :model="form">
        <el-form-item label="账号" :label-width="formLabelWidth">
          <el-input v-model="form.name"  placeholder="请输入账号"></el-input>
        </el-form-item>
        <el-form-item label="密码" :label-width="formLabelWidth">
          <el-input v-model="form.region"  placeholder="请输入密码" type="password">
          </el-input>
        </el-form-item>
      </el-form>
      <div slot="footer" class="dialog-footer">
        <el-button @click="dialogFormVisible = false">取 消</el-button>
        <el-button type="primary" @click="dialogFormVisible = false"
          >登 录</el-button
        >
      </div>
    </el-dialog>
  </el-menu>
</template>

<script>
export default {
  name: 'menu_list',
  data () {
    return {
      activeIndex: '1',
      activeIndex2: '1',
      dialogTableVisible: false,
      dialogFormVisible: false,
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      },
      formLabelWidth: '70px'
    }
  },
  methods: {
    handleSelect (key, keyPath) {
      console.log(key, keyPath)
    },
    Complaint () {
      console.log(111)
    }
  }
}
</script>

<style lang="less" scoped>
.el-menu-demo {
  padding-left: 40px;
  .is-active {
    color: #0777dd !important;
  }
  .el-menu-item {
    margin-left: 30px;
    color: #333;
    font-size: 16px;
  }
}
.complaint_bt{
  float: right;
  margin-top: 0.5%;
  margin-right: 10%;
}
/deep/.login_window{
  .el-dialog{
    width: 35%;
  }
}
</style>
