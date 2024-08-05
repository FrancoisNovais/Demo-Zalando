<script setup>
const props = defineProps({
  cart: {
    type: Array,
    required: true
  }
})
</script>

<template>
  <header>
    <!-- Premier bloc -->
    <div class="headerTop">
      <!-- Wrapper -->
      <div class="container">
        <p>Essayez d’abord, <span>payez après</span></p>
        <p>LIVRAISON & RETOUR <span>GRATUITS*</span></p>
        <p>Retour et <span>remboursement</span></p>
      </div>
    </div>

    <!-- Deuxième bloc -->
    <div class="headerBottom">
      <!-- Wrapper -->
      <div class="container">
        <nav>
          <a>Femme</a>
          <a>Homme</a>
          <a>Enfant</a>
        </nav>

        <img src="../assets/img/logo.svg" alt="Logo Zalando" />

        <nav>
          <!-- Les icônes -->
          <font-awesome-icon :icon="['far', 'user']" />
          <font-awesome-icon :icon="['far', 'heart']" />
          <font-awesome-icon :icon="['fas', 'shopping-bag']" />

          <!-- Pastille affichant le nombre d'article dans le panier -->
          <!-- Grâce à la directive 'v-if', cette balise est visible seulement si le panier à au minimum un article -->
          <p class="num-of-product" v-if="cart.length > 0">{{ cart.length }}</p>
        </nav>
      </div>
    </div>
  </header>
</template>

<style scoped>
/* -- HEADER TOP ------------------- */
.headerTop {
  background-color: var(--light-grey);
}
.headerTop .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: var(--header-top-height);
  color: var(--dark-grey);
  font-size: 12px;
}
span {
  color: var(--main-orange);
}
/* -- HEADER BOTTOM ------------------- */
.headerBottom {
  border-bottom: 1px solid #d0d1d3;
}
.headerBottom .container {
  height: var(--header-bottom-height);
  display: flex;
  justify-content: space-between;
  align-items: center;
}
img {
  width: 155px;
  /* Changer l'aspect de la souris lorsqu'elle survole l'élément */
  cursor: pointer;
  /* Bordure temporaire pour visualiser le bloc */
  /* border: 1px solid green; */
}
nav {
  flex: 1;
  /* Bordure temporaire pour visualiser le bloc */
  /* border: 1px solid green; */
}
nav {
  display: flex;
  gap: 10px;
  flex: 1;
}
nav:last-of-type {
  justify-content: flex-end;
  position: relative;
}
nav a {
  font-weight: bold;
  padding: 10px 15px;
  cursor: pointer;
}
nav a:first-child {
  background-color: var(--main-black);
  color: white;
}
svg {
  color: var(--main-black);
  padding: 10px;
  /* Pour éviter le décalage de l'icône au moment du survol de la souris, on définit une bordure de base. N'hésitez pas à commenter la propriété pour constater la différence */
  border: 2px solid white;
  /* Pour éviter que le padding décale l'icône dans une partie non visible, on doit exclure la marge interne et les bordures de la taille du SVG */
  box-sizing: content-box;
  cursor: pointer;
}
svg:hover {
  border: 2px solid var(--main-black);
}
.num-of-product {
  position: absolute;
  top: -2px;
  right: -2px;
  background-color: var(--main-orange);
  padding-top: 1px;
  width: 20px;
  height: 20px;
  border-radius: 50%;
  font-size: 14px;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
