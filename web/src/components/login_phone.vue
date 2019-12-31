<template>
  <div class="login_phone">
    <el-form :model="form_msg" :rules="rule" lazy="true" ref="form_msg">
      <el-form-item prop="phone">
        <el-input v-model.number="form_msg.phone" placeholder="手机号"></el-input>
      </el-form-item>
      <el-form-item prop="password">
        <el-input type="password" v-model="form_msg.password" placeholder="密码"></el-input>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" @click="login_phone('form_msg')">登录</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  name: "login_phone",
  data() {
    return {
      form_msg: {
        phone: "",
        password: ""
      },
      rule: {
        phone: [
          {
            required: true,
            message: "请输入手机号",
            trigger: ["blur", "change"]
          },
          { type: "number", message: "请输入数字", trigger: ["blur", "change"] }
        ],
        password: [
          { required: true, message: "请输入密码", trigger: ["blur", "change"] }
        ]
      }
    };
  },
  methods: {
    //登录事件，表单验证通过后请求登录接口
    login_phone(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          window.console.log(JSON.stringify(this.form_msg));
        } else {
          window.console.log("error submit!!");
          return false;
        }
      });
    }
  }
};
</script>

<style>
.login_phone {
  padding-top: 25px;
}
</style>