<script setup lang="js">
import { defineProps } from 'vue';

defineProps({
    title: String,
    price: Number,
    imgUrl: String
})
</script>

<template>
  <div class="card">
    <img :src="imgUrl" />
    <p>{{ title }}</p>
    <p>${{ price }}</p>
  </div>
</template>

<style scoped>
.card {
  width: 30%;
  padding: 0.5rem;
  background-color: rgb(56, 56, 56);
  border-radius: 12px;
}

.card:hover {
  border: 1px solid #0084ff;
}

img {
  width: 100%;
  border-radius: 6px;
}
</style>
