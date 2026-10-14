<template>
  <header class="header">
    <h1>TokoKita</h1>
    <nav>
      <a href="#">Beranda</a> | 
      <a href="#">Produk</a> | 
      <a href="#">Bantuan</a>
    </nav>
  </header>
</template>

<style scoped>
.header {
  background-color: #2c3e50;
  color: white;
  padding: 15px 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.header a {
  color: white;
  text-decoration: none;
  margin: 0 10px;
}
.header a:hover {
  text-decoration: underline;
}
</style>