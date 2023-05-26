<template>
  <LoadingSpinner v-if="loading" />
  <div v-else class="container">
    <h1>APP</h1>
    <h2>My Favorite Post: {{ favorite }}</h2>
    <PaginatePosts
      class="mb-2"
      :start="start"
      :end="end"
      :max-number-of-posts="posts.length"
      @evt-previous="previous"
      @evt-next="next"
    />
    <ButtonCounter class="mb-2" />
    <button-counter class="mb-2" />
    <BlogPost
      :id="991"
      title="Post 1"
      body="Description 1"
      class="mb-2"
      @evt-chg-fav="changeFavorite"
    />
    <BlogPost
      :id="992"
      title="Post 2"
      body="Description 2"
      class="mb-2"
      @evt-chg-fav="changeFavorite"
    />
    <BlogPost
      :id="993"
      title="Post 3"
      body="Description 3"
      class="mb-2"
      @evt-chg-fav="changeFavorite"
    />
    <BlogPost
      v-for="post in posts.slice(start, end)"
      :id="post.id"
      :key="post.id"
      :title="post.title"
      :body="post.body"
      class="mb-2"
      @evt-chg-fav="changeFavorite"
    />
  </div>
</template>

<script setup lang="ts">
import { ref, type Ref } from "vue";
import BlogPost from "./components/BlogPost.vue";

import ButtonCounter from "./components/ButtonCounter.vue";
import LoadingSpinner from "./components/LoadingSpinner.vue";
import PaginatePosts from "./components/PaginatePosts.vue";

const favorite = ref("");
const changeFavorite = (title: string) => {
  favorite.value = title;
};

const numberOfPosts: number = 10;
const start: Ref<number> = ref(0);
const end: Ref<number> = ref(numberOfPosts);
const loading: Ref<boolean> = ref(true);

const next = (): void => {
  start.value = end.value;
  end.value += numberOfPosts;
};

const previous = (): void => {
  start.value -= numberOfPosts;
  end.value -= numberOfPosts;
};

const posts: Ref = ref([{ id: 0, title: "", body: "" }]);
fetch("https://jsonplaceholder.typicode.com/posts")
  .then((res) => res.json())
  .then((data) => (posts.value = data))
  .catch((e) => console.log(e))
  .finally(() => (loading.value = false));
</script>

<style scoped></style>
