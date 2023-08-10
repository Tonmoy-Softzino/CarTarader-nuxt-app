<script setup>
const error = useError();

const handleGoBack = () => {
  navigateTo("/");
};
</script>

<template>
  <div class="flex font-thin items-center justify-center h-screen flex-col">
    <div class="customClass">{{ error.statusCode }}</div>
    <p class="mt-7 text-4xl">{{ error.message }}</p>
    <button
      @click="handleGoBack"
      class="rounded text-2xl mt-7 bg-slate-700 px-7 py-4"
    >
      Go Home
    </button>
  </div>
</template>

<style scoped>
.customClass {
  font-size: 4rem;
}
button {
  border-radius: 0.31rem;
  background-color: rgb(18, 18, 78);
  color: white;
  margin-top: 1rem;
  padding: 0.31rem 0.51rem;
}
</style>
