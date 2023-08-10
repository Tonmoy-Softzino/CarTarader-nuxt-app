<script setup>
const route = useRoute();
useHead({
  title: `${route.params.brand ? toTitleCase(route.params.brand) : "Cars"} in ${toTitleCase(route.params.city)}`,
});

function toTitleCase(str) {
  return str.replace(/\w\S*/g, function (txt) {
    return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
  });
}

definePageMeta({
  layout: "custom"
})
</script>

<template>
    <div>
      <div class="mt-32 flex">
        <CarSidebar />
        <NuxtPage />
      </div>
    </div>
</template>
