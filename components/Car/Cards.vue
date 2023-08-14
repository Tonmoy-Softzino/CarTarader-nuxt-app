<script setup>
const { cars } = useCars();

const favoraite = useLocalStorage("favoraite", {});

const handleFavoraite = (id) => {
  if (id in favoraite.value) {
    delete favoraite.value[id];
  } else {
    favoraite.value = {
      ...favoraite.value,
      [id]: true,
    };
  }
};
</script>

<template>
  <div class="w-full">
    <CarCard
      v-for="car in cars"
      :key="car.id"
      :car="car"
      @favour="handleFavoraite"
      :favoured="car.id in favoraite"
    />
  </div>
</template>
