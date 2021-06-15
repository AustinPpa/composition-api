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
      {title:"post title 1",body:"Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi similique exercitationem dolor illo temporibus repellat ea quisquam laborum explicabo minus iure accusantium dolorum veniam ipsam officiis animi, saepe est quasi. Lorem ipsum dolor sit amet consectetur adipisicing elit. Modi similique exercitatiLorem ipsum dolor sit amet consectetur adipisicing elit. Modi similique exercitationem dolor illo temporibus repellat ea quisquam laborum explicabo minus iure accusantium dolorum veniam ipsam officiis animi, saepe est quasi.onem dolor illo temporibus repellat ea quisquam laborum explicabo minus iure accusantium dolorum veniam ipsam officiis animi, saepe est quasi.",id:"1"},
      
      {title:"post title 2",body:"lorem ipsum",id:"2"},
    ])

    return {posts};
  }
}
</script>
