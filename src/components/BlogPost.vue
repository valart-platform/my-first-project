<template>
  <div class="card">
    <div class="card-body">
      <h5
        class="card-title"
        :class="`text-${colorText}`"
      >
        {{ id }} - {{ title }}
      </h5>
      <p>{{ body }}</p>
    </div>
  </div>
</template>

<script setup lang="ts">
interface Props {
  title: string
  id: string
  body: string
  colorText: string
}
defineProps<Props>()
</script>

<style scoped></style>
