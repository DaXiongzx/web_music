<template>
  <div>
    <el-form ref="loginForm" :model="form" :rules="rules" label-width="80px" class="login-box">
      <h3 class="login-title">欢迎</h3>
      <el-form-item label="账号" prop="username">
        <el-input type="text" placeholder="请输入账号" v-model="form.username"/>
      </el-form-item>
      <el-form-item label="密码" prop="password">
        <el-input type="password" placeholder="请输入密码" v-model="form.password"/>
      </el-form-item>
      <el-form-item>
        <el-button type="primary" v-on:click="onSubmit('loginForm')">登录</el-button>
        <el-button type="primary" >注册</el-button>
      </el-form-item>
    </el-form>

    <el-dialog
      title="温馨提示"
      :visible.sync="dialogVisible"
      width="30%"
      :before-close="handleClose">
      <span>请输入账号和密码</span>
      <span slot="footer" class="dialog-footer">
        <el-button type="primary" @click="dialogVisible = false">确 定</el-button>
      </span>
    </el-dialog>
  </div>
</template>

<script>
export default {
  name:"Login",
  data () {
    return {
      form:{
        username:'',
        password:''
      },
      rules:{
        username:[
          {required:true,message:'账号不可为空',trigger:'blur'}
        ],
        password:[
          {required:true,message:'账号不可为空',trigger:'blur'}
        ]
      },
      dialogVisible:false
    }
  },
  methods:{
    onsubmit(formName){
      this.$refs[formName].validate((valid)=>{
        if(valid){
          this.$router.push("/main");
        }else{
          this.dialogVisible = true;
          return false;
        }
      });
    }
  }
}
</script>

