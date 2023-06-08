<template>
  <div class="text-white bg-black text-5xl text-left mb-5 pt-5">Recommendations</div>
  <div class="flex overflow-x-auto h-60 bg-neutral-300 bg-black">
    <div v-for="anime in data" :key="anime.mal_id">
      <RecommendationCard :anime="anime" />
    </div>
  </div>
</template>

<script>
import { ref } from "vue";
import fetchData from "@/data/fetchData";
import RecommendationCard from "./cards/RecommendationCard.vue";

export default {
  components: {
    RecommendationCard,
  },
  setup() {
    const data = ref();
    fetchData("recommendations/anime").then((response) => {
      data.value = response.data;
    });
    console.log(data);
    return { data };
  },
};
</script>

<style>
</style>