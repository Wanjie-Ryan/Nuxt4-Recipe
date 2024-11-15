<template>
  <h1>
    {{ data.name }}
  </h1>
  <p>
    {{ data.rating }}
  </p>
</template>

<script setup>
const { id } = useRoute().params;

const { data, error } = await useFetch(`https://dummyjson.com/recipes/${id}`);

if (error.value) {
  throw createError({
    statusCode: error.value?.statusCode,
    message: error.value?.statusMessage,
  });
}
</script>

<style></style>
