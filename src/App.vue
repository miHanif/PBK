<template>
  <div class="layout-tokokita">
    <HeaderToko @gantiHalaman="halamanAktif = $event" />
    
    <main class="konten-utama">
      
      <div v-if="halamanAktif === 'beranda'" class="halaman-beranda">
        <h2>Selamat Datang di TokoKita</h2>
        <p>Pusat belanja kebutuhan Anda. Silakan klik menu <strong>Produk</strong> di atas untuk melihat daftar barang kami.</p>
      </div>

      <div v-else-if="halamanAktif === 'produk'">
        <ProductCard />
      </div>

      <div v-else-if="halamanAktif === 'katalog'">
        <KatalogTokoKita /> 
      </div>

    </main>

    <FooterToko />
  </div>
</template>

<script setup>
import { ref } from 'vue'

import HeaderToko from './TugasMinggu1/Header.vue'
import FooterToko from './TugasMinggu1/Footer.vue'
import ProductCard from './TugasMinggu1/ProductCard.vue'
import KatalogTokoKita from './TugasMinggu3/KatalogTokoKita.vue'

const halamanAktif = ref('beranda')
</script>

<style scoped>
:global(body) {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

.layout-tokokita {
  display: flex;
  flex-direction: column;
  min-height: 100vh;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

.konten-utama {
  flex: 1;
  padding: 20px;
}

.halaman-beranda {
  text-align: center;
  margin-top: 50px;
}
</style>