<template>
  <header>
    <div class="headerTop">
      <div class="container">
        <p>Essayez d'abord, <span>payez après</span></p>
        <p>LIVRAISON & RETOUR <span>GRATUITS</span>*</p>
        <p>Retour et <span>remboursement</span></p>
      </div>
    </div>
    <div class="headerBottom">
      <div class="container">
        <nav>
          <a href="#">Femme</a>
          <a href="#">Homme</a>
          <a href="#">Enfants</a>
        </nav>
        <img src="../assets/img/logo.svg" alt="Logo Zalando" />
        <nav>
          <!-- Les icônes -->
          <font-awesome-icon :icon="['far', 'user']" />
          <font-awesome-icon :icon="['far', 'heart']" />
          <font-awesome-icon :icon="['fas', 'shopping-bag']" />
        </nav>
      </div>
    </div>
  </header>
</template>

<style scoped>
/* --Header Top---------------------- */
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

/* --Header Bottom ---------------------- */
.headerBottom {
  border-bottom: 1px solid var(--light-grey);
}
.headerBottom .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: var(--header-bottom-heigh);
}
a {
  color: inherit;
  font-weight: bold;
  padding: 10px 15px;
}
a:first-child {
  background-color: var(--main-black);
  color: white;
}
img {
  width: 155px;
  /* border: 1px solid green; */
}
nav {
  display: flex;
  gap: 10px;
  /* border: 1px solid green; */
  flex: 1;
}
nav:last-of-type {
  justify-content: flex-end;
}
svg {
  color: var(--main-black);
  padding: 10px;
  border: 2px solid white;
  cursor: pointer;
}
svg:hover {
  border-color: var(--main-black);
}
</style>
