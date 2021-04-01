<template>
  <router-view />
</template>

<script>
export default {
  name: 'app',
  created () {
    document.title = '红黑榜'
  }
}
</script>

<style lang="less" scoped>
</style>
