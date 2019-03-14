<template>
    <div>
      <router-view/>
      <ul class="footer">
        <li class="icons"> <router-link :to="{name:'list'}">新闻列表</router-link></li>
        <li class="icons"> <router-link :to="{name:'user'}">个人中心</router-link></li>
      </ul>
    </div>
</template>

<script>
    export default {
        name: "Home"
    }
</script>

<style scoped>
  ul{list-style: none}
.footer{
  width: 100%;
  height: 60px;
  position: fixed;
  border-top:1px solid #eee;
  bottom: 0;
  background:#eee;
}
  .icons{font-size:20px;
    line-height: 60px;
    float: left;
    width:30%;
    text-align: center;

  }
</style>
