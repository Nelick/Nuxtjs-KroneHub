<script setup lang="ts">

const { data: posts } = await useFetch('https://jsonplaceholder.typicode.com/posts')

</script>

<template>
  <div>
    <h1>Home</h1>
    <ul>
      <li v-for="post in posts" :key="post.id">
        {{ post.title }}
      </li>
    </ul>
      </div>
</template>

<style scoped>
li {
  list-style: none;
  margin: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  background-color: #f9f9f9;
}

</style>