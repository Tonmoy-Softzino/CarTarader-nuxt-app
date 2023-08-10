<script setup>
  const props = defineProps({
    description: String,
  })
</script>

<template>
  <div class="mt-5 border-b pb-4">
    <p class="mt-5">
      {{ description }}
    </p>
  </div>
</template>
