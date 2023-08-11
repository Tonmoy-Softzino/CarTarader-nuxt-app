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
        <NuxtErrorBoundary>
          <CarSidebar />
          <NuxtPage />
          <template #error="{ error }">
            <div class="flex flex-col text-center mx-auto">
              <h1 class="text-5xl text-red-600 mb-4">Something went wrong</h1>
              <code class="mt-4">{{ error }}</code>
              <button class="bg-slate-700 text-white px-1 py-3 mt-4" @click="error.value=null">Go back</button>
            </div>
          </template>
        </NuxtErrorBoundary>
      </div>
    </div>
</template>
