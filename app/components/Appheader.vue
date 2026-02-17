<script setup lang="ts">
import "../assets/style.css";
import { RouterLink } from "vue-router";

</script>

<template>
  <div>
    <h1 class="text-3xl font-bold underline">KroneHub</h1>
    <nav>
      <ul>
       <li><NuxtLink to="/">Home</NuxtLink></li>
       <li><NuxtLink to="/about">About</NuxtLink></li>
       <li><NuxtLink to="/contact">Contact</NuxtLink></li>
      </ul>
    </nav>
  </div>
</template>

<style scoped></style>