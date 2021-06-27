<template>
  <h1>Post List</h1>
  <div v-for="post in posts" :key="post.id">
      <SInglePost :post="post"></SInglePost>
  </div>
</template>

<script>
import { onMounted, onUnmounted, onUpdated } from '@vue/runtime-core'
import SInglePost from './SInglePost'


export default {
  components: { SInglePost },
    props:["posts"],
    setup(props){
        onMounted(()=>console.log("component mounted"));
        onUnmounted(()=>console.log("component unmounted"));
        onUpdated(()=>{
          console.log("component updated")
        })
    }
}
</script>

<style>

</style>