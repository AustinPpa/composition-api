<template>
  <div class="home">
    
      <PostLists :posts="posts"></PostLists>
    
  </div>
  
</template>

<script>

import PostLists from '../components/PostLists'
import { computed, ref } from '@vue/runtime-core'

export default {
  components: { PostLists },
  setup(){
    
    let posts=ref([
      
    ])

    return {posts};
  }
}
</script>
