<template>
  <div class="card">
    <h4>{{ product.name }}</h4>
    <p>Harga: Rp {{ product.price.toLocaleString('id-ID') }}</p>
    <div class="actions">
      <button @click="$emit('buy', product)" class="btn-buy">🛒 Beli</button>
      <button @click="$emit('favorite', product)" class="btn-fav">❤️ Favorit</button>
    </div>
  </div>
</template>

<script setup>
defineProps({
  product: {
    type: Object,
    required: true
  }
})

defineEmits(['buy', 'favorite'])
</script>

<style scoped>
.card {
  border: 1px solid #ccc;
  padding: 15px;
  margin: 10px;
  border-radius: 8px;
  width: 200px;
  background: #fff;
}
.actions {
  display: flex;
  gap: 10px;
  margin-top: 10px;
}
.btn-buy { background: #4caf50; color: white; border: none; padding: 5px 10px; cursor: pointer; }
.btn-fav { background: #ff9800; color: white; border: none; padding: 5px 10px; cursor: pointer; }
</style>