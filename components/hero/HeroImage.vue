<template>
  <div class="hero__container">
    <img class="hero__image" src="~assets/images/offer.png" />
  </div>
</template>

<style scoped>
.hero__container {
  display: flex;
  justify-content: center;
  width: 100%;
}

.hero__image {
  width: 100%;
  height: auto;
}
@media only screen and (min-width: 1600px) {
  .hero__container {
    width: 80%;
  }
}
</style>
