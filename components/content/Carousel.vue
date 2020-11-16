<template>
  <div class="carousel__container">
    <div v-for="(card, index) in cards" :key="index" class="carousel__col">
      <Card :offer="card" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      cards: [
        {
          destination: 'Menorca',
          duration: '8 dias / 7 noches',
          image:
            'https://www.hola.com/imagenes/viajes/20190211137137/menorca-en-invierno-baleares/0-646-457/menorca-noche-mahon-t.jpg?filter=w600&filter=ds75',
        },
        {
          destination: 'Menorca',
          duration: '8 dias / 7 noches',
          image:
            'https://www.hola.com/imagenes/viajes/20190211137137/menorca-en-invierno-baleares/0-646-457/menorca-noche-mahon-t.jpg?filter=w600&filter=ds75',
        },
        {
          destination: 'Menorca',
          duration: '8 dias / 7 noches',
          image:
            'https://www.hola.com/imagenes/viajes/20190211137137/menorca-en-invierno-baleares/0-646-457/menorca-noche-mahon-t.jpg?filter=w600&filter=ds75',
        },
        {
          destination: 'Menorca',
          duration: '8 dias / 7 noches',
          image:
            'https://www.hola.com/imagenes/viajes/20190211137137/menorca-en-invierno-baleares/0-646-457/menorca-noche-mahon-t.jpg?filter=w600&filter=ds75',
        },
      ],
    }
  },
}
</script>
