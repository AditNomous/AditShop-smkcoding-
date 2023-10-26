<template>
    
    <div class="kepala">
    <h1>keranjang</h1>
    </div>

    <div class="cart-page">
      <h2>Keranjang Belanja</h2>
      <img style="width: 200px; margin-left: auto; margin-right: auto;" src="img/BG.jpg" alt="kosong">
      <div v-if="cartItems.length === 0">
        <p>Keranjang belanja tidak ada apa apa.</p>
      </div>
  
      <div v-else>
        <div class="cart-items">
          <div v-for="item in cartItems" :key="item.id" class="cart-item">
            <div class="item-details">
              <img :src="item.imageUrl" alt="Gambar Produk">
              <h3>{{ item.name }}</h3>
            </div>
            <div class="item-quantity">
              <input type="number" v-model="item.quantity" min="1" @change="updateCartItem(item)">
            </div>
            <div class="item-price">{{ formatCurrency(item.price) }}</div>
            <div class="item-total">{{ formatCurrency(item.price * item.quantity) }}</div>
            <button @click="removeFromCart(item.id)">Hapus</button>
          </div>
        </div>
  
        <div class="cart-summary">
          <p>Total Harga: {{ formatCurrency(cartTotal) }}</p>
          <button @click="checkout">Checkout</button>
        </div>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        cartItems: [], // Daftar item dalam keranjang belanja
      };
    },
    methods: {
      formatCurrency(price) {
        return new Intl.NumberFormat('id-ID', { style: 'currency', currency: 'IDR' }).format(price);
      },
      updateCartItem(item) {
        // Logika untuk memperbarui jumlah item dalam keranjang belanja
        // Anda dapat menambahkan kode yang sesuai di sini
      },
      removeFromCart(itemId) {
        // Logika untuk menghapus item dari keranjang belanja
        // Anda dapat menambahkan kode yang sesuai di sini
      },
      checkout() {
        // Logika untuk proses checkout
        // Anda dapat menambahkan kode yang sesuai di sini
      },
    },
    computed: {
      cartTotal() {
        // Menghitung total harga dari semua item dalam keranjang
        return this.cartItems.reduce((total, item) => total + item.price * item.quantity, 0);
      },
    },
  };
  </script>
  
  <style scoped>
  .cart-page {
    padding: 20px;
  }
  
  .cart-items {
    display: flex;
    flex-direction: column;
  }
  
  .cart-item {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 10px;
  }
  
  .item-details img {
    max-width: 100px;
    max-height: 100px;
  }
  
  button {
    background-color: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 10px;
    cursor: pointer;
  }
  </style>
  