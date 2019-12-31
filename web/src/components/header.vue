<template>
  <div id="header">
    <router-link to="/Login">登录</router-link>
    <div id="nav">
      <el-dropdown>
        <span class="el-dropdown-link">
          <i class="el-icon-s-fold"></i>
        </span>
        <el-dropdown-menu slot="dropdown">
          <el-dropdown-item>
            <router-link to="/">首页</router-link>
          </el-dropdown-item>
          <el-dropdown-item>
            <router-link to="/Msg">留言</router-link>
          </el-dropdown-item>
        </el-dropdown-menu>
      </el-dropdown>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style>
#header {
  width: 1000px;
  margin: 0 auto;
  overflow: hidden;
}
#nav {
  float: right;
}
.el-dropdown-link {
  cursor: pointer;
  color: #3e5a37;
}
.el-dropdown-link {
  font-size: 30px;
}
</style>