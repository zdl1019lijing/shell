<template>
    <div>
      <ul>
        <li v-for="(item,index) in pageLists" :key="index">
          <p class="tib1">{{item.title}}</p>
          <p class="tib2">{{item.content}}</p>
        </li>
      </ul>
    </div>
</template>

<script>
  import store from "@/store"
    export default {
        name: "List",
        store,
      computed:{
        pageLists(){
         return store.state.lists
        }
      }
    }
</script>

<style scoped>
.tib1{
  line-height: 30px;
  color:#333;
font-size:24px;
border-bottom:1px solid #ccc;}
.tib2{
  background:#eee;
  font-size:15px;
  color:#666;
}
</style>
