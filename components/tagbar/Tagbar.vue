<template>
  <div class="background-tagbar">
    <div class="tagbar">
      <div class="tagbar__info">
        <p class="text-sm">TODAS LAS</p>
        <p class="text-md">CATEGORIAS</p>
      </div>
      <div class="tagbar__categories">
        <nuxt-link
          v-for="(category, index) in categories"
          :key="index"
          to="#"
          >{{ category }}</nuxt-link
        >
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      categories: [
        'paquetes',
        'cruceros',
        'circuitos',
        'costas',
        'parques',
        'chollos',
        'vuelos',
        'hoteles',
        'trenes',
        'ferries',
        'destinos',
      ],
    }
  },
}
</script>
<style scoped>
.background-tagbar {
  width: 100vw;
  background-color: #164e7f;
}
.tagbar {
  width: 100%;
  padding: 0 10px;
  margin: auto;
  display: flex;
  justify-content: space-between;
  text-align: center;
  color: white;
}

.tagbar a {
  text-decoration: none;
  text-transform: uppercase;
  color: inherit;
  font-size: small;
  padding: 15px 12px;
}

.tagbar__categories {
  display: flex;
  flex-wrap: nowrap;
}

.tagbar__info {
  flex-grow: 1;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  padding: 5px 14px;
  background-color: #0d3467;
}
@media only screen and (min-width: 1200px) {
  .tagbar {
    width: 90%;
    justify-content: center;
    padding: 0;
  }
}

@media only screen and (min-width: 1400px) {
  .tagbar {
    width: 70%;
  }
}
</style>
