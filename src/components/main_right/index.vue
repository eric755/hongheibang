<template>
  <el-aside class="main_right" width="200px">
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <span>热门标签</span>
      </div>
      <el-row>
        <el-button v-for="o in 9" :key="o" size="small" round
          >长安马自达</el-button
        >
      </el-row>
    </el-card>
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <span>最新投诉</span>
      </div>
      <el-row>
        <div class="block">
          <el-timeline>
            <el-timeline-item timestamp="2018/4/12" placement="top">
              <el-card>
                <h4>上汽大众-途岳车辆无法启动</h4>
                <p>王小虎 提交于 2018/4/12 20:46</p>
              </el-card>
            </el-timeline-item>
            <el-timeline-item timestamp="2018/4/3" placement="top">
              <el-card>
                <h4>上汽通用-别克君越30H挂不上</h4>
                <p>王小虎 提交于 2018/4/3 20:46</p>
              </el-card>
            </el-timeline-item>
            <el-timeline-item timestamp="2018/4/2" placement="top">
              <el-card>
                <h4>奇瑞汽车-瑞虎X3前档自然玻璃</h4>
                <p>王小虎 提交于 2018/4/2 20:46</p>
              </el-card>
            </el-timeline-item>
          </el-timeline>
        </div>
      </el-row>
    </el-card>
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <span>车型投诉排行</span>
      </div>
      <el-row>
        <el-table :data="tableData" style="width: 100%">
          <el-table-column type="index" :index="indexMethod"> </el-table-column>
          <el-table-column prop="name" label="品牌名称" width="180">
          </el-table-column>
        </el-table>
      </el-row>
    </el-card>
  </el-aside>
</template>

<script>
export default {
  data () {
    return {
      tableData: [
        {
          date: '2016-05-02',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1518 弄',
          zip: 200333,
          tag: '家'
        },
        {
          date: '2016-05-04',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1517 弄',
          zip: 200333,
          tag: '公司'
        },
        {
          date: '2016-05-01',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1519 弄',
          zip: 200333,
          tag: '家'
        },
        {
          date: '2016-05-03',
          name: '王小虎',
          province: '上海',
          city: '普陀区',
          address: '上海市普陀区金沙江路 1516 弄',
          zip: 200333,
          tag: '公司'
        }
      ]
    }
  },
  methods: {
    indexMethod (index) {
      return index * 1
    }
  }
}
</script>
<style lang="less" scoped>
.main_right {
  padding: 1%;
  width: 300px !important;
  background-color: #fff !important;
  .text {
    font-size: 14px;
  }

  .item {
    margin-bottom: 18px;
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
    float: left;
    width: 99%;
    text-align: left;
    line-height: normal;
    margin: 2% 1% 0 0;
  }
  .block {
    ul {
      padding-left: 0;
    }
    float: left;
    clear: both;
    width: 99%;
    text-align: left;
    line-height: normal;
  }
}
</style>
