<template>
  <main class="product-list">
    <h2>Katalog Produk</h2>
    <div class="grid-produk">
      <ProductCard 
        v-for="produk in daftarProduk" 
        :key="produk.id" 
        :produk="produk"
      />
    </div>
  </main>
</template>

<script setup>
import { ref } from 'vue'
import ProductCard from './ProductCard.vue'

const daftarProduk = ref([
  { 
    id: 1, 
    nama: 'Laptop Asus ROG', 
    harga: 15000000, 
    stok: 10, 
    kategori: 'Elektronik' 
  },
  { 
    id: 2, 
    nama: 'Kemeja Flanel Pria', 
    harga: 150000, 
    stok: 25, 
    kategori: 'Pakaian Pria' 
  },
  { 
    id: 3, 
    nama: 'Sepatu Lari Nike', 
    harga: 1200000, 
    stok: 15, 
    kategori: 'Pakaian Pria' 
  },
  { 
    id: 4, 
    nama: 'Blus Wanita Motif Bunga', 
    harga: 120000, 
    stok: 30, 
    kategori: 'Pakaian Wanita' 
  },
  { 
    id: 5, 
    nama: 'Headphone Bluetooth Sony', 
    harga: 450000, 
    stok: 50, 
    kategori: 'Elektronik' 
  }
])
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