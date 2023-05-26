<template>
  <div class="btn-group" role="group" aria-label="Basic example">
    <button
      type="button"
      class="btn btn-outline-primary"
      :disabled="start <= 0"
      @click="emitEvent('evt-previous')"
    >
      Previous {{ start }}
    </button>
    <button
      type="button"
      class="btn btn-outline-primary"
      :disabled="end >= maxNumberOfPosts"
      @click="emitEvent('evt-next')"
    >
      Next {{ end }}
    </button>
  </div>
</template>

<script setup lang="ts">
interface Props {
  start: number;
  end: number;
  maxNumberOfPosts: number;
}
defineProps<Props>();
interface Emits {
  (event: "evt-previous"): void;
  (event: "evt-next"): void;
}
const emitEvent = defineEmits<Emits>();
</script>

<style scoped></style>
