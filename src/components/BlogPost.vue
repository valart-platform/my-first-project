<template>
  <div class="card">
    <div class="card-body">
      <h5 class="card-title">{{ id }} - {{ title }}</h5>
      <p>{{ body }}</p>
      <button class="btn btn-outline-primary" @click="emitEvent('evt-chg-fav', title)">
        Favorite
      </button>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Props {
  id: number;
  title: string;
  body: string;
}
defineProps<Props>();
interface Emits {
  (event: "evt-chg-fav", title: string): void;
}
const emitEvent = defineEmits<Emits>();
</script>

<style scoped></style>
