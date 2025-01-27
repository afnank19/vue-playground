<script setup lang="ts">
import { onMounted, ref } from "vue";
import Card from "./components/card.vue";

const title = "Xbox Series X Controller";

const products = ref([]);

onMounted(async () => {
  try {
    const response = await fetch("https://api.escuelajs.co/api/v1/products");

    const data = await response.json();

    console.log(data);

    products.value = data;
  } catch (error) {
    console.error(error);
  }
});
</script>

<template>
  <h1>Vue Store Ltd</h1>
  <div class="container">
    <Card
      v-for="(product, index) in products"
      :key="index"
      :title="product.title"
      :price="product.price"
      :img-url="product.images[0]"
    />
  </div>
</template>

<style scoped>
.container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 0.5rem;
}

h1 {
  text-align: center;
}
</style>
