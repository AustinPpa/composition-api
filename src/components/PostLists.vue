<template>
  <h1>Post List</h1>
  <div v-for="post in posts" :key="post.id">
      <SInglePost :post="post"></SInglePost>
  </div>
</template>

<script>
import SInglePost from './SInglePost'


export default {
  components: { SInglePost },
    props:["posts"],
    setup(props){
        console.log(props.posts)
    }
}
</script>

<style>

</style>