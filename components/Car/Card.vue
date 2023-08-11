<script setup>
const props = defineProps({
  car: Object,
});
</script>

<template>
  <div
    class="w-full shadow border overflow-hidden mb-5 h-[12.2rem] cursor-pointer" @click="navigateTo(`/car/${car.name}-${car.id}`)"
  >
    <div class="flex h-full">
      <img
        :src="props.car.url"
        alt="Toyota"
        class="w-[18rem] h-full"
      />
      <div class="p-4 flex flex-col">
        <div>
          <h1 class="text-2xl text-slate-900">{{ props.car.name }}</h1>
          <p class="text-gray-700 overflow-auto">
            {{ props.car.description }}
          </p>
        </div>
        <h1 class="mt-auto text-xl text-green-700">
          <span class="text-yellow-600">$</span> {{ props.car.price }}
        </h1>
      </div>
    </div>
  </div>
</template>
