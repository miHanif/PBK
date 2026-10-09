<template>
<div class="produk-container">
   <h2>Produk yang Tersedia</h2> 

  <div class="card">
  <h3>Sepatu Olahraga</h3>
  <p>Rp 250.000</p>
  <button>Tambah ke Keranjang</button>
  </div>
  </div>
</template>


<style scoped>
.produk-container {
  max-width: fit-content;
  margin: 50px auto;
  padding: 20px;
  font-family: sans-serif;
}

.card {
  border: 1px solid #ccc;
  border-radius: 8px;
  padding: 15px;
  width: 200px;
  text-align: center;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}


.card button {
  background-color: #42b883;
  color: white;
  border: none;
  padding: 10px 15px;
  border-radius: 4px;
  cursor: pointer;
  width: 100%;
}


.card button:hover {
  background-color: #33a06f;
}
</style>
