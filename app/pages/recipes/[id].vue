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

useSeoMeta({
  title: data.value?.name,
  description: "Recipes for you to cook",
  ogTitle: data.value?.name,
  ogDescription: "Recipes for you to cook",
  ogImage: data.value?.image,
  ogUrl: `http://localhost:3000/recipes/${data.value?.id}`,
  twitterTitle: data.value?.name,
  twitterDescription: "Recipes for you to cook",
  twitterImage: data.value?.image,
  twitterCard: "summary",
});

useHead({
  htmlAttrs: {
    lang: "en",
  },
  link: [
    {
      rel: "icon",
      type: "image/png",
      href: "/favicon.png",
    },
  ],
});
</script>

<style></style>
