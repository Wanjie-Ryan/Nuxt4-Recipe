<template>
  <header class="py-4 border-b">
    <nav class="container flex items-center">
      <NuxtLink to="/" class="flex items-center gap-1">
        <NuxtImg src="/logo.png" alt="Logo" format="webp" width="56px" />
        <span class="text-xl font-bold">My Recipes</span>
      </NuxtLink>
      <ul class="flex gap-6 ml-auto text-xl font-bold capitalize">
        <li>
          <NuxtLink to="/">Home</NuxtLink>
        </li>
        <li>
          <NuxtLink to="/about">About</NuxtLink>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
// import { NuxtImg } from '#build/components';

export default {};
</script>

<style></style>
