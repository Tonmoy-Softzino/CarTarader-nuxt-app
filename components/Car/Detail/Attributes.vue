<script setup>
  const props = defineProps({
    features: Array,
  })
</script>

<template>
    <div class="mr-10 mt-5 border-b pb-5 w-full">
      <div class="flex text-md mt-2" v-for="feature in features" :key="feature">
        <p class="rounded text-lime-900 mr-3">✔</p>
        <p class="rounded text-lime-900 mr-3">{{ feature }}</p>
      </div>
      <!-- <div class="flex text-md mt-2">
        <p class="rounded text-lime-900 mr-3">✔</p>
        <p class="rounded text-lime-900 mr-3">AI inclusion</p>
      </div> -->
    </div>
</template>