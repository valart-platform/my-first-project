<template>
  <div>
    <button class="btn btn-outline-primary" @click="increment">
      Counter {{ counter }}
    </button>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";
const counter = ref(0);
const increment = () => counter.value++;
</script>

<style scoped></style>
