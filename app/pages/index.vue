<template>
  <main>
    <section class="bg-[#f1f1f1]">
      <div class="container flex items-center gap-10 py-20 lg:flex-row">
        <div class="flex-1 order-2 text-center lg:order-1 lg:text-left">
          <h1 class="mb-6 text-4xl font-extrabold lg:text-6xl text-balance">
            Master the Kitchen with Ease; Unleash Your Inner chef today
          </h1>

          <p class="mb-8 text-xl lg:text-2xl text-balance">
            Discover recipes helping you to find the easiest way to cook
          </p>

          <button
            class="px-4 py-2 text-lg text-white rounded-md cursor-pointer selft-start bg-dodgeroll-gold"
          >
            Browse recipes
          </button>
        </div>
        <div class="flex-1 order-1 lg:order-2">
          <NuxtImg
            src="/logo.png"
            sizes="xs:100vw sm:667px"
            format="webp"
            densities="x1"
            alt=""
          />
        </div>
      </div>
    </section>
    <section class="container py-20">
      <h2 class="mb-2 text-3xl lg:text5xl">Discover, Create, Share</h2>
      <p class="mb-8 text-lg lg:text-xl">Check out our most popular recipes</p>
      <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-x-4 gap-y-8">
        <div v-for="recipe in data?.recipes" class="flex flex-col rounded-md shadow">
          <NuxtImg :src="recipe.image" sizes="xs:100vw sm:50vw lg:400px" format="webp" densities="x1" alt="" class="rounded-t-md"/>
          <div class="flex flex-col flex-1 px-4 py-6">
            <p>{{recipe.name}}</p>
            <p>{{ recipe.cookTimeMinutes }}</p>
            <p>{{recipe.caloriesPerSaving}}</p>
            <p>{{ recipe.rating }}{{ recipe.reviewCount }}</p>
            
            <NuxtLink :to="`recipes/${recipe.id}`" class="self-start px-4 py-2 text-base text-white bg-yellow-400 rounded-md cursor-pointer lg:text-lg">View</NuxtLink>
          </div>
          
        </div>

        
      </div>


      
    </section>
  </main>
</template>

<script setup>
// const {data, error} = await useAsyncData('recipes', ()=> $fetch('https://dummyjson.com/recipes?limit=12'))

const { data, error } = await useFetch(
  "https://dummyjson.com/recipes?limit=12"
);
console.log("recipe data", data.value);
</script>

<style></style>
