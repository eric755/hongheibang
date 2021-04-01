<template>
  <el-row type="flex" class="top row-bg" justify="space-between">
    <!-- logo -->
    <el-col class="bg-purple-dark-box" :span="6">
      <div class="grid-content bg-purple-dark">
        <img class="logo" src="@/assets/logo.png" alt="logo" />
      </div>
    </el-col>

    <!-- 搜索 -->
    <el-col class="bg-purple-light-box" :span="8">
      <div class="grid-content bg-purple-light">
        <!-- 搜索框 -->
        <el-input
          placeholder="请输入关键词"
          v-model.trim="searchValue"
          clearable
        >
          <el-button slot="append" icon="el-icon-search" @click="search"
            >搜索投诉</el-button
          >
        </el-input>
        <!-- 历史记录 -->
        <el-tag
          class="tag_item"
          size="small"
          v-for="tag in tags"
          :key="tag.name"
          closable
          :disable-transitions="false"
          @close="handleClose(tag)"
          @click="lishi(tag.name)"
        >
          {{ tag.name }}
        </el-tag>
      </div>
    </el-col>

    <!-- 登录注册 -->
    <el-col class="bg-purple-box" :span="6">
      <div class="grid-content bg-purple">
        <div class="lgoin_box">
          <i class="el-icon-user-solid"></i>
          <el-link :underline="false">登录</el-link>|<el-link :underline="false"
            >注册</el-link
          >
        </div>
      </div>
    </el-col>
  </el-row>
</template>

<script>
export default {
  name: 'top',
  data () {
    return {
      nameValue: '',
      searchValue: '',
      tags: [
        { name: '北京现代' },
        { name: '宝马' },
        { name: '科鲁兹' },
        { name: '蒙迪欧' },
        { name: '凯迪拉克' },
        { name: '创酷' }
      ]
    }
  },
  methods: {
    search () {
      const filters = {}
      filters.name = this.nameValue // 'name' || 'id'
      filters.value = this.searchValue // 具体值
      if (filters.value === '') {
        this.$message.warning('搜索内容不能为空')
      } else {
        this.$emit('searchEvent', filters)
      }
    },
    handleClose (tag) {
      this.tags.splice(this.tags.indexOf(tag), 1)
      console.log(tag)
    },
    lishi (list) {
      this.searchValue = list
      console.log(list)
    }
  }
}
</script>

<style lang="less" scoped>
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
  .logo {
    max-width: 100%;
    max-height: 100%;
  }
  height: 100%;
}
/deep/.bg-purple-light {
  color: #fff;
  .el-input__inner:focus {
    border-color: #ffd04b;
    outline: 0;
  }
  .el-input__inner {
    border-radius: 20px;
    border-top-right-radius: 0;
    border-bottom-right-radius: 0;
    color: #fff;
    background: transparent;
  }
  .el-input-group__append {
    border-radius: 20px;
    border-top-left-radius: 0;
    border-bottom-left-radius: 0;
  }
  .el-button {
    color: #0777dd;
  }
  .el-tag {
    border: 0;
    color: #0777dd;
    background-color: #fff;
  }
}
.bg-purple-dark-box,
.bg-purple-light-box,
.bg-purple-box {
  display: flex;
  align-items: center;
  justify-content: center;
}
.grid-content {
  border-radius: 4px;
  min-height: 36px;
}
.row-bg {
  height: 107px;
  color: #fff;
}
.tag_item {
  float: left;
  margin-right: 1%;
}
.lgoin_box {
  border: 1px solid #fff;
  padding: 0px 20px;
  border-radius: 18px;
  i.el-icon-user-solid {
    text-align: center;
    font-size: 22px;
    vertical-align: middle;
    padding-right: 5px;
  }
  .el-link {
    color: #fff;
    font-size: 16px;
    padding: 0px 5px;
  }
  .el-link:hover {
    color: #fdc936;
  }
}
</style>
