<script setup>
import { ref } from 'vue'

const post = ref(null)

async function fetchdata() {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts/1')
  post.value = await res.json()
}

fetchdata()
</script>

<template>
  <div>
    <p>ID: {{ post.id }}</p>
    <p>タイトル: {{ post.title }}</p>
    <p>本文: {{ post.body }}</p>
  </div>
</template>