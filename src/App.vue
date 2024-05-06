<template>
  <h1>{{ message }}</h1>

  <button @click="increment">Tambah</button> <!-- Tombol yang, saat diklik, akan menambah nilai count -->
  <p>Jumlah: {{ count }}</p> <!-- Menampilkan nilai count dalam template -->
  <input v-model="text" placeholder="type here">
  <p>{{ text }}</p>
  <h1 v-bind:class='tittleClass'>this is me</h1>
  <h1 v-bind:id='dynamicId'>this is you</h1>

</template>

<script setup>
import { ref, onUpdated } from 'vue' //<!-- Mengimpor ref untuk reaktivitas dan onUpdated untuk lifecycle hook -->

const count = ref(0)
const message = ref('syifa nur medina') //<!-- Membuat variabel reaktif bernama count dengan nilai awal 0 -->
const text = ref('')
const tittleClass = ref ('title')
const dynamicId = ref ('title')

onUpdated(() => { //<!-- Lifecycle hook yang dieksekusi setiap kali komponen diperbarui -->
  console.log("Komponen diperbarui") //<!-- Pesan konsol yang menunjukkan bahwa komponen telah diperbarui -->
})

function increment() {//{ <!-- Fungsi yang menambah nilai count setiap kali dipanggil -->
  count.value += 1 //<!-- Menambah nilai count sebanyak 1 -->
}
</script>

<style>
.title {
  color:chocolate
}
#title {
  color:crimson
}

</style>
