<template>
  <div class="left">
    <div class="logo">
      <i-tooltip content="Back to welcome" placement="bottom" style="cursor: pointer;">
        <div @click="$router.push({name: 'welcome', params: {force: 'force'}})">
          <img src="~@/assets/logo.png" alt="Hve" width="80px" height="80px">
        </div>
        Hve
      </i-tooltip>
      <p>A static blog build tool.</p>
    </div>
    <i-menu active-name="1" width="160px" @on-select="changeMenu">
      <i-menu-item name="post-list">
        <span class="text">๐ ๆ็ซ </span>
      </i-menu-item>
      <i-menu-item name="theme">
        <span class="text">๐ ไธป้ข</span>
      </i-menu-item>
      <i-menu-item name="page">
        <span class="text">๐ ้กต้ข</span>
      </i-menu-item>
      <i-menu-item name="setting">
        <span class="text">๐  ้็ฝฎ</span>
      </i-menu-item>
      <i-menu-item name="resource">
        <span class="text">๐ฆ ่ตๆบ</span>
      </i-menu-item>
    </i-menu>
    <div class="btns">
      <backup></backup>
      <br><br>
      <preview></preview>
      <br><br>
      <publish></publish>
    </div>
  </div>
</template>

<script>
import Preview from './preview/Preview'
import Publish from './publish/Publish'
import Backup from './backup/Backup'
export default {
  components: {
    Preview,
    Publish,
    Backup,
  },
  data() {
    return {}
  },
  methods: {
    changeMenu(active) {
      this.$router.push({
        name: active,
      })
    },
  },
}
</script>

<style lang="scss" scoped>
.ivu-menu-item {
  padding: 10px 24px;
}
.left {
  width: 160px;
  height: 100%;
  position: fixed;
  top: 0;
  left: 0;
  background: #fff;
  border-right: 1px solid #dddee1;
  .logo {
    width: 90%;
    min-height: 60px;
    text-align: center;
    line-height: 30px;
    font-size: 18px;
    margin: 15px auto;
    p {
      font-size: 12px;
    }
  }
  .btns {
    width: 100%;
    padding: 10px;
    position: absolute;
    bottom: 20px;
    left: 0;
  }
}
</style>