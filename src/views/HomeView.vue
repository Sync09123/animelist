<template>
<div class="bg-black">

 

  

  <RecommendationView/>
  <ScheduleView/>

</div>
</template>

<script>


import RecommendationView from './components/RecommendationView.vue';
import ScheduleView from './components/ScheduleView.vue';
// @ is an alias to /src


export default {
  name: 'HomeView',
  components: {
    RecommendationView,
    ScheduleView


  },

  
}
</script>

<style>

</style>