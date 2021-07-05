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
import getPosts from "../composables/getPosts"
import PostLists from '../components/PostLists'

export default {
  components: { PostLists },
  setup(){
    //composable function
    let {posts,error,load}=getPosts() //{posts,error,load}

    load();
    
    return {posts,error};
  }
}
</script>
