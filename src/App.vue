<script setup>
import { RouterLink, RouterView } from "vue-router";
</script>

<template>
  <header>
    <div class="wrapper">
      <nav class="space-x-5 flex justify-center content-center">
        <!-- <RouterLink to="/">Home</RouterLink> -->
        <!-- <RouterLink to="/about">About</RouterLink> -->
      </nav>
      <div class="my-5">
        <h1 class="text-center text-3xl font-bold">
          Todo App with Vue 3 and Tailwind CSS
        </h1>
      </div>
    </div>
  </header>

  <RouterView />
</template>
