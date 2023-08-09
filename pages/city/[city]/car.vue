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
</script>

<template>
  <div>
    <Navbar />
    <div
      class="mx-auto mt-4 max-w-7xl space-y-4 px-4 xs:px-8 sm:px-10 lg:px-16 pb-16 w-3/5 font-light"
    >
      <div class="mt-32 flex">
        <CarSidebar />
        <NuxtPage />
      </div>
    </div>
  </div>
</template>
