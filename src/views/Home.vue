<template>
  <div class="home">  
<h1>Understanding Setup fn in composition APIS - reactive and refs </h1>

<div v-for="name in matchingNames" :key="name"> {{name}}</div>

<input type="text" v-model="search">

<p>Search term: {{search}}</p>


  </div>
</template>

<script>
import {ref, computed } from '@vue/reactivity'

export default {
  name: 'Home',
  setup(){

   const names = ref(['Saka', 'SmithRow', 'Aoba', 'Odegard', 'Nenny'])

   const search = ref("")

   const matchingNames = computed(() => {

     return names.value.filter((name)=> name.includes(search.value) )


   })

    return {names, search, matchingNames}



  },
}
</script>
