<script setup>
import { ref } from 'vue'

import Header from './TugasMinggu4/TokoKita/Header.vue'
import Footer from './TugasMinggu4/TokoKita/Footer.vue'
import ProductCard from './TugasMinggu5/ProductCard.vue'

const products = ref([
  { id: 1, name: 'Barang A', price: 10000, category: 'Tes', stock: 10, rating: 5 }, // > 5
  { id: 2, name: 'Barang B', price: 20000, category: 'Tes', stock: 3, rating: 4 },  // 1-5
  { id: 3, name: 'Barang C', price: 30000, category: 'Tes', stock: 0, rating: 4 }   // 0
])
</script>

<template>
  <div class="app-layout">
    <Header />

    <main class="main-content">
      <h2>Katalog Produk</h2>
      <div class="product-grid">
        <ProductCard
          v-for="product in products"
          :key="product.id"
          :name="product.name"
          :price="product.price"
          :category="product.category"
          :stock="product.stock"
          :rating="product.rating"
        />
      </div>
    </main>

    <Footer />
  </div>
</template>

<style>
body {
  margin: 0;
  padding: 0;
  font-family: Arial, sans-serif;
}

.app-layout {
  display: flex;
  flex-direction: column;
  min-height: 100vh; 
}

.main-content {
  flex: 1; 
  padding: 20px;
}

.product-grid {
  display: flex;
  flex-wrap: wrap;
  gap: 15px;
}
</style>