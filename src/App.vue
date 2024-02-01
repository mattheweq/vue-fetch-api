<template>

<div class="mx-auto flex flex-col items-center sm:max-w-[1200px] sm:grid sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-5">

<div class="fade-in-slow flex flex-col justify-center">
  <p class="text-7xl">/|\v/|\</p>
  <p>Discography</p>
</div>

 <div class="fade-in" v-for="album in apiData" :key="album.id">
  <a :href="album.spotifyUrl" target="_blank">

    <div class="p-2 mb-0 flex flex-col">
      <p class="bg-yellow-300 w-fit font-bold">{{ album.title }}</p>
      <p class="bg-yellow-300 w-fit text-center text-sm ml-auto sm:ml-0">{{ album.year }}</p>
    </div>
    
    <div class="info cursor-pointer">
      <p>
        <span class="cta">Listen on Spotify</span>
      </p>
      <img class="p-2 pt-0 w-48" :src="album.artwork" :alt="album.title">
    </div>

  </a>
</div>

</div> 

</template>

<script setup>
  import {onMounted, ref} from 'vue';

  const apiData = ref([]);

  const getData = async() => {
    return fetch("https://mvmapi.olk1.com/albums").then(response => response.json());
  }

  onMounted(() => {
    getData().then(data => {
      apiData.value = data.reverse();
    });
  });
</script>