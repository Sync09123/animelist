<template>
<div class="home">
  <img alt="Vue logo" src="../assets/logo.png">

  <div v-for="anime in data" :key="anime.mal_id">
  {{ anime.entry[0].title }}
  
  <img :src="anime.entry[0].images.jpg.image_url">
  </div>

</div>
</template>

<script>
import fetchData from '@/data/fetchData';
import { ref } from 'vue';
// @ is an alias to /src


export default {
  name: 'HomeView',
  components: {

  },

  setup(){
    
    const data = ref()
    fetchData( 'recommendations/anime').then(response =>{
    data.value = response.data
  })
  console.log(data)
  return {data}
}
}
</script>
