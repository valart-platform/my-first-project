<template>
  <div class="container">
    <h1>APP</h1>
    <ButtonCounter />
    <button-counter />
    <BlogPost
      id="1"
      title="Post 1"
      body="Description 1"
      color-text="primary"
    />
    <BlogPost
      id="2"
      title="Post 2"
      body="Description 2"
      color-text="secondary"
    />
    <BlogPost
      id="3"
      title="Post 3"
      body="Description 3"
      color-text="success"
    />
    <BlogPost
      v-for="post in posts"
      :id="post.id"
      :key="post.id"
      :title="post.title"
      :body="post.body"
      :color-text="post.colorText"
    />
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import BlogPost from './components/BlogPost.vue'
import ButtonCounter from './components/ButtonCounter.vue'
const posts = ref([
  { title: 'Post 1', id: '1', body: 'Description 1', colorText: 'primary' },
  { title: 'Post 2', id: '2', body: 'Description 2', colorText: 'secondary' },
  { title: 'Post 3', id: '3', body: 'Description 3', colorText: 'success' }
])
</script>

<style scoped></style>
