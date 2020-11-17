<template>
  <div class="content__container">
    <ContentHeader />
    <ContentCarousel />
  </div>
</template>

<style scoped>
.content__container {
  flex-grow: 1;
  width: 100%;
  padding: 0 20px;
  display: flex;
  flex-direction: column;
  justify-content: flex-start;
}
@media only screen and (min-width: 1200px) {
  .content__container {
    width: 90%;
    padding: 0;
  }
}

@media only screen and (min-width: 1400px) {
  .content__container {
    width: 70%;
  }
}
</style>
