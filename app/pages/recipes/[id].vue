<template>

  
</template>

<script setup>

const {id} = useRoute().params;

const {data, error} = await useFetch(`https://dummyjson.com/recipes/${id}`);

</script>

<style>

</style>