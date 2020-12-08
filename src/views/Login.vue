<template>
  <div class="login">
    <div class="login-box">
      <el-form
        :model="loginForm"
        :rules="loginFormRules"
        ref="loginForm"
        label-width="55px"
        class="form"
      >
        <el-row>
          <el-form-item label="账号:" prop="account">
            <el-input v-model="loginForm.account"></el-input>
          </el-form-item>
        </el-row>
        <el-row>
          <el-form-item label="密码:" prop="password">
            <el-input v-model="loginForm.password"></el-input>
          </el-form-item>
        </el-row>
        <el-row>
          <el-form-item class="button-item">
            <el-button type="info" @click="resetLoginForm">重 置</el-button>
            <el-button type="primary" @click="login">登 录</el-button>
          </el-form-item>
        </el-row>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loginForm: {
        account: '',
        password: ''
      },
      loginFormRules: {
        account: [{ required: true, message: '请输入账号', trigger: 'blur' }],
        password: [{ required: true, message: '请输入密码', trigger: 'blur' }]
      }
    }
  },
  methods: {
    resetLoginForm() {
      this.$refs.loginForm.resetFields()
    },
    login() {
      this.$router.push({ name: 'List' })
    }
  }
}
</script>

<style lang="scss" scoped>
.login {
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #c0c4cc;
  .login-box {
    width: 35%;
    height: 40%;
    min-width: 300px;
    background-color: #fff;
    border-radius: 7px;
    margin: 0 auto;
    display: flex;
    justify-content: center;
    align-items: center;
    .form {
      width: 100%;
      height: 62%;
      padding: 0 30px;
      .el-form-item {
        width: 100%;
        height: 100%;
      }
    }
  }
}
.button-item {
  display: flex;
  justify-content: flex-end;
}
</style>
