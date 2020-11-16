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
