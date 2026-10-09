<template>
  <div class="katalog-container">
    <h2>Katalog Mini TokoKita</h2>

    <div class="search-bar">
      <input 
        type="text" 
        v-model="searchQuery" 
        placeholder="Cari nama produk..." 
      />
    </div>

    <div class="produk-grid">
      <div 
        v-for="produk in filteredProducts" 
        :key="produk.id" 
        class="produk-card"
      >
        <h3>{{ produk.nama }}</h3>
        
        <!-- Menampilkan kategori -->
        <p class="kategori">Kategori: {{ produk.kategori }}</p>
        
        <!-- Menampilkan harga -->
        <p class="harga">Harga: Rp{{ produk.harga.toLocaleString('id-ID') }}</p>
        <p class="stok">Sisa Stok: {{ produk.stok }}</p>

        <div class="aksi">
          <button v-if="produk.stok > 0" @click="beli(produk.id)" class="btn-beli">
            Beli
          </button>
          <span v-else class="stok-habis">Stok habis</span>

          <!-- Tombol Tambah Stok -->
          <button @click="tambahStok(produk.id)" class="btn-tambah">
            Tambah Stok
          </button>
        </div>
      </div>
    </div>

    <!-- Pesan jika produk tidak ditemukan saat mencari -->
    <p v-if="filteredProducts.length === 0" class="not-found">
      Produk tidak ditemukan.
    </p>
  </div>
</template>

<script setup>
import { ref, computed } from 'vue'

// Data Produk
const products = ref([
  { id: 1, nama: 'Laptop ASUS ROG', harga: 25000000, stok: 5, kategori: 'Elektronik' },
  { id: 2, nama: 'Mouse Wireless Logitech', harga: 150000, stok: 0, kategori: 'Aksesoris' },
  { id: 3, nama: 'Keyboard Mechanical', harga: 1200000, stok: 10, kategori: 'Aksesoris' },
  { id: 4, nama: 'Monitor Dell 27 Inch', harga: 3500000, stok: 2, kategori: 'Elektronik' },
  { id: 5, nama: 'Meja Kerja Minimalis', harga: 850000, stok: 0, kategori: 'Furnitur' },
  { id: 6, nama: 'Kursi Ergonomis', harga: 1500000, stok: 3, kategori: 'Furnitur' }
])

const searchQuery = ref('')

const filteredProducts = computed(() => {
  if (!searchQuery.value) return products.value
  
  return products.value.filter(p => 
    p.nama.toLowerCase().includes(searchQuery.value.toLowerCase())
  )
})

const tambahStok = (id) => {
  const produk = products.value.find(p => p.id === id)
  if (produk) {
    produk.stok++
  }
}

const beli = (id) => {
  const produk = products.value.find(p => p.id === id)
  if (produk && produk.stok > 0) {
    produk.stok--
  }
}
</script>

<style scoped>
.katalog-container {
  max-width: 800px;
  margin: 40px auto;
  padding: 20px;
  font-family: sans-serif;
}
.search-bar {
  margin-bottom: 25px;
}
.search-bar input {
  width: 100%;
  padding: 12px;
  font-size: 16px;
  border: 1px solid #ccc;
  border-radius: 6px;
  box-sizing: border-box;
}
.produk-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
  gap: 20px;
}

.produk-card {
  border: 1px solid #ddd;
  border-radius: 8px;
  padding: 15px;
  background-color: #fcfcfc;
  box-shadow: 0 4px 6px rgba(0,0,0,0.05);
}
.produk-card h3 {
  margin-top: 0;
  margin-bottom: 5px;
  font-size: 1.2em;
}
.kategori {
  font-size: 0.85em;
  color: #7f8c8d;
  margin-top: 0;
}
.harga {
  font-weight: bold;
  font-size: 1.1em;
  color: #2c3e50;
  margin-bottom: 5px;
}
.stok {
  color: #d35400;
  font-weight: 500;
  margin-top: 0;
}

/* Styling Tombol dan Status */
.aksi {
  margin-top: 20px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
button {
  padding: 8px 12px;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-weight: bold;
  font-size: 0.9em;
}
.btn-beli {
  background-color: #2ecc71;
  color: white;
}
.btn-beli:hover {
  background-color: #27ae60;
}
.btn-tambah {
  background-color: #3498db;
  color: white;
}
.btn-tambah:hover {
  background-color: #2980b9;
}
.stok-habis {
  color: #e74c3c;
  font-weight: bold;
  font-style: italic;
  font-size: 0.9em;
}
.not-found {
  text-align: center;
  color: #7f8c8d;
  margin-top: 30px;
  font-style: italic;
}
</style>