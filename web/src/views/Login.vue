<template>
<div id="login">
  <img src="../assets/img/timg.jpg" class="login_banner">
  <div class="login-card">
    <el-card shadow="always">
      <el-tabs v-model="activeName" @tab-click="handleClick">
        <el-tab-pane name="login_phone">
          <span slot="label" class="tabs_label">手机登录</span>
          <LoginPhone />
        </el-tab-pane>
        <el-tab-pane name="login_email">
          <span slot="label" class="tabs_label">邮箱登录</span>
          <LoginEmail />
        </el-tab-pane>
      </el-tabs>
    </el-card>
  </div>
</div>
</template>

<script>
import LoginPhone from "../components/login_phone";
import LoginEmail from "../components/login_email";

export default {
  name: "login",
  components: {
    LoginPhone,
    LoginEmail
  },
  data: function() {
    return {
      login_components: "login_phone",
      activeName: "login_phone"
    };
  },
  methods: {
    handleClick(tab, event) {
      window.console.log(tab, event);
    }
  }
};
</script>

<style>
#login{
  width: 1000px;
  margin: 0 auto;
  overflow: hidden;
}
.login-card {
  width: 368px;
  margin-top: 150px;
  float: right;
  /* border: 1px solid red; */
}
.tabs_label{
  font-size: 18px;
  padding: 35px;
}
.login_banner{
  height: 550px;
  margin-top: 60px;
  margin-left: 40px;
}
</style>

