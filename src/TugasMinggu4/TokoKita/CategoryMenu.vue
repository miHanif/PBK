<template>
  <aside class="menu-kategori">
    <h3>Kategori</h3>
    <ul>
      <li><a href="#">Semua Produk</a></li>
      <li><a href="#">Elektronik</a></li>
      <li><a href="#">Pakaian Pria</a></li>
      <li><a href="#">Pakaian Wanita</a></li>
    </ul>
  </aside>
</template>

<style scoped>
.menu-kategori {
  width: 200px;
  background-color: #f4f4f4;
  padding: 20px;
  border-radius: 8px;
  height: fit-content;
}
.menu-kategori h3 {
  margin-top: 0;
  border-bottom: 2px solid #ddd;
  padding-bottom: 10px;
}
.menu-kategori ul {
  list-style: none;
  padding: 0;
}
.menu-kategori li {
  margin-bottom: 10px;
}
.menu-kategori a {
  text-decoration: none;
  color: #333;
}
.menu-kategori a:hover {
  color: #3498db;
}
</style>