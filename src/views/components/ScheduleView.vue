<template>
  <div class="text-white text-5xl text-left mb-5 pt-5">Schedule</div>

 <div class="grid grid-cols-2 gap-5">
    <div v-for="anime in data" :key="anime.mal_id">
      <div class="flex  rounded-lg w-full hover:bg-slate-800 ease-in-out duration-300 ">
        <img
          :src="anime.images.jpg.image_url"
          class="w-40 h-40  rounded-l-lg"
        />

        <div class="flex flex-col text-white p-2 text-lg">
          <div class="flex text-start text-2xl font-bold">
            {{ anime.title }}
          </div>

          <div class="flex text-gray-300">
            Duration:

            {{ anime.duration }}
          </div>
          <div class="flex text-gray-300">
            Status:

            <div class="text-green-400">{{ anime.status }}</div>

          </div>


          <div class="flex text-gray-300">
            Title:

            <div class="text-yellow-400">{{ anime.title_english }}</div>
        </div>
      </div>
    </div>
  </div>
  </div>
</template>


<script>
import { ref } from "vue";
import fetchData from "@/data/fetchData";
export default {
  setup() {
    const data = ref();
    fetchData("schedules").then((response) => {
      data.value = response.data;
    });
    console.log(data);
    return { data };
  },
};
</script>

<style>
</style>