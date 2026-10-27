<template>
  <div class="app-container">
    <header class="header">
      <h2>Toko Mini Vue</h2>
      <div class="cart-info">
        <p><strong>🛒 Total Keranjang:</strong> {{ cartCount }} item</p>
        <p v-if="lastBoughtProduct" class="highlight">
          <strong>Terakhir dibeli:</strong> {{ lastBoughtProduct }}
        </p>
      </div>
    </header>

    <div class="product-grid">
      <ProductCard
        v-for="item in products"
        :key="item.id"
        :product="item"
        @buy="handleBuy"
        @favorite="handleFavorite"
      />
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue'
import ProductCard from './TugasMInggu6/ProductCard.vue'

const cartCount = ref(0)
const lastBoughtProduct = ref('')

const products = ref([
  { id: 1, name: 'Laptop Gaming', price: 15000000 },
  { id: 2, name: 'Mouse Wireless', price: 250000 },
  { id: 3, name: 'Mechanical Keyboard', price: 850000 },
  { id: 4, name: 'Monitor 144Hz', price: 3200000 },
  { id: 5, name: 'Headset Bluetooth', price: 600000 }
])

const handleBuy = (product) => {
  cartCount.value++
  lastBoughtProduct.value = product.name
}

const handleFavorite = (product) => {
  alert(`${product.name} telah ditambahkan ke daftar favorit!`)
}
</script>

<style scoped>
.app-container { font-family: Arial, sans-serif; padding: 20px; background: #f4f4f9; min-height: 100vh; }
.header { background: #2c3e50; color: white; padding: 15px; border-radius: 8px; margin-bottom: 20px; }
.cart-info { margin-top: 10px; background: rgba(255,255,255,0.1); padding: 10px; border-radius: 5px; }
.highlight { color: #f1c40f; }
.product-grid { display: flex; flex-wrap: wrap; gap: 15px; }
</style>