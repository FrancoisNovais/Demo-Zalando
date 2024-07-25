<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Details from './components/Details.vue'

// Import du fichier JSON contenant les informations relatives au produit
import productInfos from './assets/data.json'
console.log(productInfos)
</script>

<template>
  <div>
    <div class="wrapper">
      <Header />
      <main>
        <div class="container">
          <div></div>

          <Details :productInfos="productInfos" />
        </div>
      </main>

      <Footer />
    </div>
  </div>
</template>

<style scoped>
.container {
  display: flex;
  height: calc(
    100vh - var(--header-top-height) - var(--header-bottom-height) - var(--footer-height)
  );
  border: 1px solid green;
}
.container > div {
  border: 1px solid orange;
  width: 50%;
}
.container > div:last-child {
  padding: 25px 0 25px 100px;
  box-sizing: border-box;
}
</style>
