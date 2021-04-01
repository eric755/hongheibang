<template>
  <el-footer class="foot">
    <el-row type="flex" class="row-bg" justify="space-around">
      <el-col :span="6">
        <div class="grid-content bg-purple">
          <el-link v-for="o in 4" :key="o" :underline="false" type="info"
            >友情链接<el-divider direction="vertical"></el-divider>
          </el-link>
          <el-divider content-position="right"></el-divider>

          <span
            style="
              color: rgb(147, 153, 168);
              font-family: 微软雅黑;
              font-size: 12px;
              line-height: 30px;
              background-color: rgb(37, 41, 50);
            "
            >CopyRight © 2000-2017 CNEV,All Rights Reserved. 版权所有
            杭州广拓网络科技有限公司&nbsp;
            <a
              href="javascript:;"
              target="_blank"
              style="
                color: rgb(37, 41, 50);
                font-family: 微软雅黑;
                font-size: 12px;
                line-height: 30px;
                background-color: rgb(37, 41, 50);
              "
              >网站制作</a
            ></span
          >
        </div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple-light">
          <div class="fotel">
            <div class="fotel1">
              <img src="static/picture/fotel.png" alt="" />
              <div class="">
                <span class="fo-hot">服务热线：</span>
                <span class="fo-hot2">18667168119</span>
              </div>
            </div>
            <div class="ewm-m">工作时间：周一至周五 9:00-17:00</div>
          </div>
        </div>
      </el-col>
      <el-col :span="6">
        <div class="grid-content bg-purple">
          <div class="rf">
            <div class="ewmk">
              <img
                src="https://www.cnev.cn/content/index/images/ewm2.jpg"
                alt=""
              />
              <div class="ewm-m">关注微信公众号</div>
            </div>
          </div>
        </div>
      </el-col>
    </el-row>
  </el-footer>
</template>

<script>
export default {}
</script>

<style lang="less" scoped>
.foot {
    line-height: normal !important;
  color: #fff !important;
  .el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    color: #fff;
  }
  .bg-purple {
    color: #fff;
  }
  .bg-purple-light {
    color: #fff;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
  }
}
</style>
