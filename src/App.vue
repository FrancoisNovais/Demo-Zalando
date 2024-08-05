<script setup>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Details from './components/Details.vue'

// Import du fichier JSON contenant les informations relatives au produit
import data from './assets/data.json'

import { reactive, ref } from 'vue'

const productInfos = reactive(data)

const selectedVariant = ref(data.variants[0])

const cart = reactive([])

const changeVariant = (variant) => {
  selectedVariant.value = variant
}

const addToCart = () => {
  cart.push(selectedVariant)
  console.log(selectedVariant)
}
</script>

<template>
  <div>
    <div class="wrapper">
      <Header :cart="cart" />
      <main>
        <div class="container">
          <div>
            <img :src="selectedVariant.image.url" :alt="selectedVariant.image.alt" />
          </div>

          <Details
            @addProductToCart="addToCart"
            @changeSelectedVariant="changeVariant"
            :productInfos="productInfos"
            :selectedVariant="selectedVariant"
          />
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
  /* border: 1px solid green; */
}
.container > div {
  /* border: 1px solid orange; */
  width: 50%;
}
.container > div:last-child {
  padding: 25px 0 25px 100px;
  box-sizing: border-box;
}
.container > div:first-child {
  padding: 25px;
}
img {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
</style>
