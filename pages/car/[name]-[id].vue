<script setup>
const route = useRoute();

const {cars} = useCars();

const car = computed(() => {
  return cars.find((c) =>{
    return c.id === parseInt(route.params.id)
  })
})

const { toTitleCase} = useUtilities();

useHead({
  title: toTitleCase(route.params.name)
})
if(!car.value){
  throw createError({
    statusCode: 404,
    message: `Car not found of id ${route.params.id}`
  })
}

definePageMeta({
  layout: "custom",
});
</script>

<template>
    <div>
      <CarDetailHero :car="car"/>

      <CarDetailAttributes :features = "car.features"/>

      <CarDetailDescription :description="car.description"/>

      <CarDetailContact />
    </div>
</template>
