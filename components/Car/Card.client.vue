<script setup>
import heartField from "@/assets/images/heartFilled.png";
import heartOutline from "@/assets/images/heartOutline.png";


const props = defineProps({
  car: Object,
  favoured: Boolean,
});

const emit = defineEmits(['favour'])

// const favour = useState(`favour-${props.car.id}`, () => {
//   return false;
// });
</script>

<template>
  <div
    class="w-full shadow border relative overflow-hidden mb-5 h-[200px] cursor-pointer"
  >
    <img :src="favoured ? heartField : heartOutline" alt="" class="absolute w-7 top-5 z-20 right-5" @click="emit('favour', car.id)">
    <div class="flex h-full" @click="navigateTo(`/car/${car.name}-${car.id}`)">
      <NuxtImg
        :src="props.car.url"
        alt="Toyota"
        class="w-[300px] h-full"
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
