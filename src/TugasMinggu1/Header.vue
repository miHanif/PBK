<template>
  <header class="header-toko">
    <h1>TokoKita</h1>
    <nav>
      <ul>
        <li>
          <a href="#" @click.prevent="$emit('gantiHalaman', 'beranda')">Beranda</a>
        </li>
        <li>
          <a href="#" @click.prevent="$emit('gantiHalaman', 'produk')">Produk</a>
        </li>
        <li>
          <a href="#" @click.prevent="$emit('gantiHalaman', 'katalog')">Katalog</a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script setup>
defineEmits(['gantiHalaman'])
</script>

<style scoped>
.header-toko {
  background-color: #2c3e50;
  color: white;
  padding: 15px 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.header-toko h1 {
  margin: 0;
}
nav ul {
  list-style: none;
  padding: 0;
  margin: 0;
  display: flex;
  gap: 20px;
}
nav a {
  color: white;
  text-decoration: none;
  font-weight: bold;
}
nav a:hover {
  color: #42b883;
}
</style>