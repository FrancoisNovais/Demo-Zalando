<script setup>
// Import des composants
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Details from './components/Details.vue'

// Import du fichier JSON contenant les informations relatives au produit
import data from './assets/data.json'

// Import des fonctions 'reactive' et 'ref
import { reactive, ref } from 'vue'

// Création des valeurs réactives
const productInfo = reactive(data)
const selectedVariant = ref(data.variants[0])
const cart = reactive([])

const addToCart = (product) => {
  cart.push(product)
}

// Fontion déclenchée lorsque l'événement est entendu. Elle permet de changer la valeur de la ref 'selectedVariant'
const changeVariant = (variant) => {
  selectedVariant.value = variant
}
</script>

<template>
  <div>
    <!-- Transmission de la props 'cart' au composant 'Header.vue' -->
    <Header :cart="cart" />

    <main>
      <!-- Wrapper -->
      <div class="container">
        <!-- Première colonne -->
        <div>
          <img :src="selectedVariant.image.url" :alt="selectedVariant.image.alt" />
        </div>

        <!-- Deuxième colonne -->
        <Details
          :productInfo="productInfo"
          :selectedVariant="selectedVariant"
          @changeSelectedVariant="changeVariant"
          @addProductToCart="addToCart"
        />
      </div>
    </main>

    <Footer />
  </div>
</template>

<style scoped>
/* Ici, il s'agit de style local donc nous stylisons uniquement la balise ayant la classe 'container' qui se trouve dans ce composant. Les autres ne sont pas impactées */
.container {
  display: flex;
  height: calc(
    100vh - var(--header-top-height) - var(--header-bottom-height) - var(--footer-height)
  );
}
.container > div {
  width: 50%;
  /* Bordure temporaire pour visualiser le bloc */
  /* border: 1px solid green; */
}

/* -- Première colonne ----------- */
.container > div:first-child {
  padding: 25px;
}

img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  cursor: pointer;
}

/* -- Deuxième colonne ----------- */
.container > div:last-child {
  padding: 25px 0 25px 100px;
}
</style>
