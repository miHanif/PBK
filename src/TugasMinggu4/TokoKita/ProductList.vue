<template>
  <main class="product-list">
    <h2>Daftar Produk</h2>
    <div class="grid-produk">
      <ProductCard />
      <ProductCard />
      <ProductCard />
    </div>
  </main>
</template>

<script setup>
import ProductCard from './ProductCard.vue'
</script>

<style scoped>
.product-list {
  flex: 1; 
}
.product-list h2 {
  margin-top: 0;
}
.grid-produk {
  display: flex;
  gap: 20px;
  flex-wrap: wrap; 
}
</style>