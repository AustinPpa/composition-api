<template>
  <div class="home">
    <div v-if="error">
      {{error}}
    </div>
    <div v-if="posts.length>0">
      <PostLists :posts="posts"></PostLists>
    </div>
    <div v-else>
      loading ...
    </div>
  </div>
  
</template>

<script>

import PostLists from '../components/PostLists'
import { computed, ref } from '@vue/runtime-core'

export default {
  components: { PostLists },
  setup(){
    let posts=ref([]);
    let error=ref("");
    let load=async()=>{
      try{
        let response = await fetch("http://localhost:3000/posts")
        if(response.status===404){
          throw new Error ("not found url")
        }
        let datas = await response.json();
        
        posts.value=datas

      }catch(err){
        // console.log(error.message)
        error.value=err.message
      }
      
     
    }
    load();
    return {posts,error};
  }
}
</script>
