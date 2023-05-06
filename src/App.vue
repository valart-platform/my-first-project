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
  </div>
</template>

<script setup lang="ts">
import BlogPost from './components/BlogPost.vue'
import ButtonCounter from './components/ButtonCounter.vue'
</script>

<style scoped></style>
