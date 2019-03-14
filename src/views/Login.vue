<template>
  <div>
    <form  v-if="!isReg">
      <p class="fbl"><input type="text" placeholder="请输入手机号" v-model="name"></p>
      <p class="fbl"><input type="password" placeholder="请输入密码" v-model="password"></p>
      <button type="button"  @click="Log()" class="bt1">登录</button>
      <button type="button" @click="Reg1()" class="bt1 te1">注册</button>
    </form>
    <form v-else>
      <p class="fbl"><input type="text" placeholder="请输入手机号" v-model="name"></p>
      <p class="fbl"><input type="password" placeholder="请输入密码" v-model="password"></p>
      <p class="fbl"><input type="password" placeholder="请再次输入密码" v-model="repeat"></p>
      <button type="button" @click="adData()" class="bt1" >确定</button>
      <button type="button" @click="canCle()" class="bt1 te1">取消</button>
    </form>
  </div>
</template>

<script>
    export default {
        name: "Login",
      data(){
          return{
           isReg:false,
            name:'',
            password:'',
            repeat:''
        }
      },
        methods:{
           Log (){
             if(localStorage.getItem('name') ===this.name && localStorage.getItem('password') ===  this.password){
               this.name='',
                 this.password='',
               this.$router.push('/home/list')
             }else{
               alert('用户名或密码不正确')
             }
           },
          Reg1 (){
            this.isReg= true
          },
          canCle (){
             this.isReg= false
          },
          adData(){
             if(this.password == this.repeat) {
               localStorage.setItem("name",this.name),
                 localStorage.setItem("password",this.password)
               this.name='',
                 this.password='',
                 this.repeat='',
                 this.isReg=false
             }
             else{
               alert('两次密码输入不一致')
             }
          }
        }
    }
</script>

<style scoped>
.fbl{
  width:90%;margin: 5%;
  height:40px;}
.fbl input{
  height:35px;width: 100%;}
  .bt1{width:40%;height: 30px; margin:5%;background:#fc5151;border: none;color:#fff;}
.bt1.te1{width:40%;margin:5%;background:#ccc}
</style>
