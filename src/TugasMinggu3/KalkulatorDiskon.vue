<template>
  <div class="kalkulator-container">
    <h2>Kalkulator Diskon</h2>

    <div class="form-group">
      <label>Nama Produk:</label>
      <input type="text" v-model="productName" placeholder="Contoh: Sepatu" />
    </div>

    <div class="form-group">
      <label>Harga Awal (Rp):</label>
      <input type="number" v-model.number="price" placeholder="Masukkan harga" />
    </div>

    <div class="form-group">
      <label>Diskon (%):</label>
      <input type="number" v-model.number="discount" placeholder="Masukkan diskon" />
    </div>

    <button @click="calculate">Hitung</button>

    <div v-if="isCalculated" class="hasil">
      
      <p v-if="Number(price) <= 0" class="pesan-error">
         Harga belum diisi atau bernilai 0. Silakan masukkan harga yang valid!
      </p>

      <p v-else-if="Number(discount) < 0" class="pesan-error">
         Diskon tidak valid! Persentase tidak boleh bernilai minus (negatif).
      </p>

      <p v-else-if="Number(discount) > 100" class="pesan-error">
         Diskon tidak masuk akal! Persentase tidak boleh lebih dari 100%.
      </p>

      <div v-else>
        <h3>Detail Perhitungan:</h3>
      </div>

    </div>
    </div>
</template>

<script setup>
import { ref } from 'vue'

const productName = ref('')
const price = ref(null)
const discount = ref(null)
const finalPrice = ref(0)

const isCalculated = ref(false)

const calculate = () => {
  isCalculated.value = true 

  if (price.value > 0 && discount.value >= 0 && discount.value <= 100) {
    const cut = (price.value * discount.value) / 100
    finalPrice.value = price.value - cut
  } else {
    finalPrice.value = 0 
  }
}
</script>

<style scoped>
.kalkulator-container {
  border: 1px solid #ccc;
  padding: 20px;
  border-radius: 8px;
  margin: 50px auto;
  max-width: 400px;
  background-color: #f9f9f9;
}
.form-group {
  margin-bottom: 10px;
}
label {
  display: inline-block;
  width: 130px;
  font-weight: bold;
}
input {
  padding: 5px;
  width: 200px;
}
button {
  margin-top: 10px;
  padding: 8px 15px;
  background-color: #42b883;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}
button:hover {
  background-color: #33a06f;
}
.hasil {
  margin-top: 20px;
  padding-top: 15px;
  border-top: 2px dashed #ccc;
}
.pesan-error {
  color: #d9534f;
  font-weight: bold;
}
.pesan-info {
  color: #0275d8;
  font-style: italic;
  margin: 10px 0;
}
.harga-akhir {
  font-size: 1.2em;
  color: #42b883;
}
</style>