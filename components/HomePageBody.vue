<script setup>
    import CarSearchBar from './Car/SearchBar.vue'
</script>

<template>
    <div class="relative h-screen w-100 bg-no-repeat bg-cover bg-bottom bg-[url('/Users/tonmoy/Desktop/cartreader-app/assets/css/images/erik-mclean-AaYAElNOxsQ-unsplash.jpg')]">
      <div class="z-10 absolute w-full h-full flex justify-center items-center">
        <div class="text-center w-1/2">
          <h1 class="text-white font-extralight text-8xl mb-10 ">
            Find the best car
          </h1>
          <CarSearchBar />
        </div>
      </div>
      <div class="z-1 w-full h-full absolute opacity-70 bg-black"></div>
    </div>
</template>