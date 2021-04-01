<template>
  <el-main class="main_left">
    <el-alert
      title="红黑榜主要依据企业投诉解决率、投诉处理态度以及投诉人（用户）对处理结果综合测评计算出最好和最孬的企业，是体现企业处理投诉好（孬）的最直接表现。红黑榜每月发布一次，遇到重大侵权投诉实行动态发布，年终发布年度最好（孬）企业品牌、车型。"
      :closable="false"
      type="warning"
      show-icon
    >
    </el-alert>
    <el-card class="box-card" v-for="o in 8" :key="o">
      <div slot="header" class="clearfix">
        <span>【红榜通告】2021年04月01日</span>
        <el-button style="float: right; padding: 3px 0" type="text"
          >查看更多</el-button
        >
      </div>
      <el-card class="card_first" :body-style="{ padding: '0px' }">
        <img
          src="https://www.cnev.cn/admin/brand/brandsrc/20130724032020.jpg"
          class="image"
        />
        <div style="padding: 14px">
          <span>通用中国</span>
          <div class="bottom clearfix">
            <time class="time">{{ currentDate }}</time>
            <el-button type="text" class="button">红榜</el-button>
          </div>
        </div>
      </el-card>

      <div v-for="o in 4" :key="o" class="text item">
        <el-collapse v-model="activeName" accordion>
          <el-collapse-item title="一致性 Consistency" name="1">
          </el-collapse-item>
        </el-collapse>
      </div>
    </el-card>
    <el-pagination
      class="page_list"
      background
      layout="prev, pager, next"
      :total="1000"
    >
    </el-pagination>
  </el-main>
</template>

<script>
export default {
  data () {
    return {
      currentDate: new Date(),
      activeName: '1'
    }
  }
}
</script>

<style lang="less" scoped>
.main_left {
  text-align: left !important;
  line-height: normal !important;
  background: #fff !important;
  .time {
    font-size: 13px;
    color: #999;
  }

  .bottom {
    margin-top: 13px;
    line-height: 12px;
  }

  .button {
    padding: 0;
    float: right;
  }

  .image {
    width: 100%;
    display: block;
  }

  .clearfix:before,
  .clearfix:after {
    display: table;
    content: "";
  }

  .clearfix:after {
    clear: both;
  }
  .box-card {
    .card_first{
      img{
        width: 20%;
        margin: 2% 0 0 2%;
      }
    }
    float: left;
    width: 48%;
    margin: 0.8%;
  }
  .page_list {
    text-align: center;
    clear: both;
    display: block;
    padding: 3% 0 2% 0;
  }
}
</style>
