<template>
  <div class="login_phone">
    <el-form :model="form_msg" :rules="rule" lazy=true;>
      <el-form-item prop="Phone">
        <el-input v-model.number="form_msg.Phone"  placeholder="手机号"></el-input>
      </el-form-item>
      <el-form-item prop="Password">
        <el-input type="password" v-model="form_msg.Password" placeholder="密码"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="login_phone">登录</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  name:"login_phone",
  data() {
    return {
      form_msg: {
        Phone: "",
        Password: ""
      },
      rule: {
        Phone: [
          { required: true, message: "请输入手机号", trigger: ['blur', 'change'] },
          { type:"number" , message: "请输入数字", trigger: ['blur', 'change'] }
          ],
        Password: [
          { required: true, message: "请输入密码", trigger: ['blur', 'change'] },
          ]
      }
    };
  },
  methods: {
      login_phone() {
        window.console.log(JSON.stringify(this.form_msg));
      }
    }
};
</script>

<style>
.login_phone {
  padding-top: 25px;
}
</style>