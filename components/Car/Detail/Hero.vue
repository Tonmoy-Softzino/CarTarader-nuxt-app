<script setup>
  const props = defineProps({
    car: Object,
  })
</script>

<template>
    <div class="mt-10">
          <img
            :src="car.url"
            class="w-full"
            alt=""
          />
          <h1 class="mt-10 text-4xl">{{ car.name }}</h1>
          <div
            class="text-slate-500 text-lg border-b pb-5 flex mt-3 justify-between"
          >
            <div class="flex">
              <p class="mr-2">{{ car.seats }} seat</p>
              <p class="mr-2">|</p>
              <p class="mr-2">{{ car.miles }} miles</p>
            </div>
            <div class="font-bold text-2xl text-slate-700"><span class="text-yellow-600">$</span> {{ car.price }}</div>
          </div>
        </div>
</template>