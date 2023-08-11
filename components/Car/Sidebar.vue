<script setup>
const modal = ref({
  brand: false,
  location: false,
  price: false,
});

const updateModal = (key) => {
  modal.value[key] = !modal.value[key];
};

const router = useRoute();
const city = ref("");

const onChangeLocation = () => {
  if (!city.value) return;
  if (!isNaN(parseInt(city.value))) {
    throw createError({
      statusCode: 420,
      message: "Invalid City Name",
    });
  }
  updateModal("location");
  navigateTo(`/city/${city.value}/car/${router.params.brand}`);
};
</script>

<template>
  <div class="shadow border w-1/2 mr-10 z-30 h-[12rem]">
    <div class="p-5 flex justify-between cursor-pointer border-b relative">
      <h3>Location</h3>
      <h3 class="text-blue-800 capitalize" @click="updateModal('location')">
        {{ router.params.city }}
      </h3>
      <div
        class="absolute border shadow left-56 p-5 top-1 -m-1 bg-white"
        v-if="modal.location"
      >
        <input type="text" class="border rounded p-1" v-model="city" />
        <button
          class="bg-blue-400 w-full mt-2 rounded text-white p-1"
          @click="onChangeLocation"
        >
          Apply
        </button>
      </div>
    </div>
    <div class="p-5 flex justify-between cursor-pointer border-b relative">
      <h3>Brand</h3>
      <h3 class="text-blue-800 capitalize">Toyota</h3>
    </div>
    <div class="p-5 flex justify-between cursor-pointer border-b relative">
      <h3>Price</h3>
      <h3 class="text-red-800 capitalize">Any</h3>
    </div>
  </div>
</template>
