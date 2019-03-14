<template>
    <div>
      <router-view/>
      <router-link :to="{name:'add'}" class="adt">新闻添加</router-link>
    </div>
</template>

<script>
    export default {
        name: "User"
    }
</script>

<style scoped>
.adt{background:#fc5151;width: 40%;
  height:40px;border-radius:10px;
  color:#fff;margin:150px 30%;
  line-height: 40px;
display: block}
</style>
