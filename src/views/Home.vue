<template>
  <div class="home">  
<h1>Watch </h1>

<div v-for="name in matchingNames" :key="name"> {{name}}</div>

<input type="text" v-model="search">

<p>Search term: {{search}}</p>


  </div>
</template>

<script>
import {ref, computed } from '@vue/reactivity'
import { watch, watchEffect } from '@vue/runtime-core'

export default {
  name: 'Home',
  setup(){

   const names = ref(['Saka', 'SmithRow', 'Aoba', 'Odegard', 'Nenny'])

   const search = ref("")

   watch(search, () => {
     console.log("watch fn ran");
     console.log(search.value);
   });

   watchEffect(() => {
     console.log("watch effect fn run", search.value)
   })

   const matchingNames = computed(() => {

     return names.value.filter((name)=> name.includes(search.value) )


   })

    return {names, search, matchingNames}



  },
}
</script>
