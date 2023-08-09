<script setup>
  const city = ref("");
  const cityError = ref(false);

  const handleSearch = () => {
    if(!city.value){
      return cityError.value = true;
    }
    navigateTo(`/city/${city.value}/car`)
  }
</script>

<template>
  <div
    class="font-serif text-2xl rounded-full bg-white flex justify-between overflow-hidden drop-shadow-2xl mx-auto"
  >
    <input
      v-model="city"
      type="text"
      class="py-3 px-5 w-full rounded-full text-2xl focus:outline-none font-sans"
      :class="cityError ? 'border border-red-500' : '' "
      placeholder="Search by city..."
    />
    <button class="bg-sky-200 px-10 text-slate-500 font-sans" @click="handleSearch">Search</button>
  </div>
</template>