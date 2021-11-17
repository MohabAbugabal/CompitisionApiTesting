<template>
  <div class="home">  
<h1>Props </h1>

<PostList :posts = "posts" />
  </div>
</template>

<script>
import PostList from '../components/PostList.vue'
import {ref} from 'vue';

export default {
  name: 'Home',
  components: {
    PostList
    }
  ,
  setup(){

    const posts = ref([{
      title: 'welcome the blog',
      body: 'Hello world 1',
      id: 1
    }, 
    {
    title: 'top tips',
    body: 'Hello world 2',
    id:2
    }
    
    ])


    return {posts}



  },
}
</script>
