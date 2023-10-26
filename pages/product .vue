
<template>
<div class="ndas">
  <h1>produk</h1>
  </div>
  
    <div class="product-page">
      <div class="product-image">
        <img :src="product.imageUrl" alt="Gambar Produk">
      </div>
      <div class="product-details">
        <h1 style="font-weight: bold;" >{{product.name}}</h1>
        <p class="product-description">{{ product.description }}</p>
        <p class="product-price">Harga: {{ formatCurrency(product.price) }}</p>
        <NuxtLink to="/cart">
        <button @click="addToCart">Tambahkan ke Keranjang</button>
      </NuxtLink>
      </div>
    </div>

    
    <div class="product-page">
      <div class="product-image">
        <img src="img/buku.jpg" alt="Gambar Produk">
      </div>
      <div class="product-details">
        <h1 style="font-weight: bold;">buku biasa</h1>
        <p class="product-description">cocok untuk menulis</p>
        <p class="product-price">Harga: {{ formatCurrency(product.price) }}</p>
        <NuxtLink to="/cart">
        <button @click="addToCart">Tambahkan ke Keranjang</button>
      </NuxtLink>
      </div>
    </div>

    
    <div class="product-page">
      <div class="product-image">
        <img src="img/produk.webp" alt="Gambar Produk">
      </div>
      <div class="product-details">
        <h1 style="font-weight: bold;">Buku ajaib</h1>
        <p class="product-description">buku bacaan ajaib</p>
        <p class="product-price">Harga: {{ formatCurrency(product.price) }}</p>
        <NuxtLink to="/cart">
        <button @click="addToCart">Tambahkan ke Keranjang</button>
      </NuxtLink>
      </div>
    </div>


  </template>
  
  <script>
  export default {
    data() {
      return {
        product: {
          name: "Buku ajaib penagih hutang",
          description: "cocok untuk menambah penghasilan",
          price: 10000, 
          imageUrl: "img/buku3.jpg"
        }
        
      };
    },
    methods: {
      addToCart() {
        // kode keranjange
        alert ("ditambahkan ke keranjang");
      },
      formatCurrency(price) {
        return new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR' }).format(price);
      }
    }
  };
  </script>
  
