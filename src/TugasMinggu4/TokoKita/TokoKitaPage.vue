<template>
  <div class="halaman-utama">
    <Header />
    
    <div class="layout-tengah">
      <CategoryMenu />
      <ProductList />
    </div>

    <Footer />
  </div>
</template>

<script setup>
import Header from './Header.vue'
import CategoryMenu from './CategoryMenu.vue'
import ProductList from './ProductList.vue'
import Footer from './Footer.vue'
</script>

<style scoped>
.halaman-utama {
  display: flex;
  flex-direction: column;
  min-height: 100vh; 
  font-family: Arial, sans-serif;
}

.layout-tengah {
  display: flex;
  gap: 30px;
  padding: 20px 30px;
  flex: 1; 
}
</style>