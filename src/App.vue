<template>
  <div id="app">
    <Navbar />
    <Carousel />

    <div class="product-container">
      <ProductCard
        v-for="product in products"
        :key="product.id"
        :product="product"
        @add-to-cart="handleAddToCart"
      />
    </div>

    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Carousel from './components/Carousel.vue';
import ProductCard from './components/ProductCard.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Carousel,
    ProductCard,
    Footer
  },
  data() {
    return {
      products: [
        { id: 1, name: 'Dres Style Korean', price: 'Rp1.500.000', imgSrc: 'https://cf.shopee.co.id/file/71308215ee5ccb0e5515e570bd5355f7  ' },
        { id: 2, name: 'Jam Tangan', price: 'Rp800.000', imgSrc: 'https://s4.bukalapak.com/img/9315743123/w-1000/jam_Tangan_Pria_Sport_Swiss_Army_Original_Watch.jpg' },
        { id: 3, name: 'HandBag', price: 'Rp3.400.000', imgSrc: 'https://s4.bukalapak.com/img/919227854/w-1000/HNStylish___Tas_Import___Impor_Fashion_Korea_untuk_Wanita___.jpg' }
      ]
    };
  },
  methods: {
    handleAddToCart(product) {
      // Implementasikan logika untuk menambahkan produk ke keranjang
      console.log('Beli Sekarang:', product);
    }
  }
}
</script>

<style>
body {
  background-color: #e4e4e4;
  margin: 0;
  font-family: Arial, sans-serif;
}

.product-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  padding: 20px;
}
</style>