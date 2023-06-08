<template>
  <div class="flex-col w-40 justify-center p-2 ">
    

    <img :src="anime.entry[0].images.jpg.image_url" class="w-40 h-40 rounded-lg"/>
    
    <div class="text-white flex-auto ">
      {{ anime.entry[0].title }}
    </div>

  </div>
</template>

<script>
export default {
  props: ["anime"],
};
</script>

<style>
</style>