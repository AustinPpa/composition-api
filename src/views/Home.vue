<template>
  <div class="home">

    <input type="text" v-model="search">
    <p>Search item - {{search}}</p>
    <div v-for="name in filteredNames" :key="name">
      {{name}}
    </div>
  </div>
</template>

<script>

import { computed, ref } from '@vue/runtime-core'

export default {
  setup(){
    let names=ref(["aung aung","kyaw kyaw","su su","mg mg"]);
    let search=ref("");

    let filteredNames=computed(()=>{
      return names.value.filter(name=>{
        return name.includes(search.value)
      })
    })

    return {names,search,filteredNames};
  }
}
</script>
