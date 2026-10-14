<template>
  <div class="card">
    <div class="gambar-placeholder">{{ produk.kategori }}</div>
    
    <div class="info-produk">
      <h4>{{ produk.nama }}</h4>
      <p class="harga">Rp {{ produk.harga.toLocaleString('id-ID') }}</p>
      
      <p class="stok-barang">Sisa stok: {{ produk.stok }}</p>
      
      <button class="btn-beli">Beli Sekarang</button>
    </div>
  </div>
</template>

<script setup>
defineProps({
  produk: Object
})
</script>

<style scoped>
.card {
  width: 200px;
  border: 1px solid #ddd;
  border-radius: 8px;
  overflow: hidden;
  box-shadow: 0 2px 5px rgba(0,0,0,0.1);
  text-align: center;
  background: white;
}
.gambar-placeholder {
  background-color: #ecf0f1;
  height: 150px;
  display: flex;
  align-items: center;
  justify-content: center;
  color: #7f8c8d;
  font-size: 0.9rem;
}
.info-produk {
  padding: 15px;
}
.info-produk h4 {
  margin: 0 0 10px;
  font-size: 1.1rem;
}
.harga {
  color: #e74c3c;
  font-weight: bold;
  margin-bottom: 5px;
}
.stok-barang {
  font-size: 0.85rem;
  color: #7f8c8d;
  margin-bottom: 15px;
}
.btn-beli {
  background-color: #3498db;
  color: white;
  border: none;
  padding: 8px 15px;
  border-radius: 4px;
  cursor: pointer;
  width: 100%;
}
.btn-beli:hover {
  background-color: #2980b9;
}
</style>