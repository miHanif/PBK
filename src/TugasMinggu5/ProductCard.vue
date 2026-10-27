<script setup>
defineProps({
  name: {
    type: String,
    required: true
  },
  price: {
    type: Number,
    required: true
  },
  category: {
    type: String,
    required: true
  },
  stock: {
    type: Number,
    required: true
  },
  rating: {
    type: Number,
    required: true
  }
})
</script>

<template>
  <div class="product-card">
    <h3>{{ name }}</h3>
    <p><strong>Harga:</strong> Rp {{ price.toLocaleString('id-ID') }}</p>
    
    <!-- Menerapkan v-if, v-else-if, v-else untuk kondisi stok -->
    <div class="stock-status">
      <p v-if="stock > 5" class="stock-banyak">
        Stok Banyak ({{ stock }})
      </p>
      <p v-else-if="stock >= 1 && stock <= 5" class="stock-terbatas">
        Stok Terbatas (Sisa {{ stock }})
      </p>
      <p v-else class="stock-habis">
        Stok Habis
      </p>
    </div>

    <button :disabled="stock === 0">Beli</button>
  </div>
</template>

<style scoped>

.stock-banyak { color: green; font-weight: bold; }
.stock-terbatas { color: darkorange; font-weight: bold; }
.stock-habis { color: red; font-weight: bold; }

.product-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 16px;
  margin: 10px;
  width: 250px;
  background-color: #f9f9f9;
  box-shadow: 2px 2px 8px rgba(0,0,0,0.1);
}
.product-card h3 {
  margin-top: 0;
  color: #333;
}
.product-card p {
  margin: 4px 0;
  color: #555;
}
</style>