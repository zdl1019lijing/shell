<template>
    <div>
      <p class="btit1">标题</p>
      <p class="fbl"><input type="text" v-model="title" ></p>
      <p class="btit1">内容</p>
      <p class="fbl"><input type="text" v-model="content"></p>
      <button @click="sub()" class="adt">添加</button>
    </div>
</template>
<script>
  import store from '@/store'
    export default {
        name: "Add",
        store,
      data(){
          return{
            title:'',
            content:''
          }
      },
        methods:{
          sub(){
           store.commit('addItem',{
           title:this.title,
             content:this.content
            })
            this.title=''
            this.content=''
            this.$router.push('/home/list')
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
  .adt{background:#fc5151;width: 40%;
    height:40px;border-radius:10px;
    color:#fff;margin:30px 30%;
    line-height: 40px;
    display: block}
</style>
