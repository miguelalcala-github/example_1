<template>
  <div class="carousel__container">
    <div class="carousel__arrow-left">
      <img src="@/assets/svg/selectIcon.svg" alt="prev offers" />
    </div>
    <div v-for="(card, index) in cards" :key="index" class="carousel__col">
      <Card :offer="card" />
    </div>
    <div class="carousel__arrow-right">
      <img src="@/assets/svg/selectIcon.svg" alt="next offers" />
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
            'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522469/exercise_1/menorca_pbtaru.jpg',
          discount: '-15%',
        },
        {
          destination: 'Cancun',
          duration: '8 dias / 7 noches',
          image:
            'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522469/exercise_1/cancun_krwpsw.jpg',
          discount: '-30%',
          special: 'todo incluido',
        },
        {
          destination: 'Londres',
          duration: '8 dias / 7 noches',
          image:
            'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522468/exercise_1/londres_pbvkav.jpg',
          discount: '-30%',
        },
        {
          destination: 'Menorca',
          duration: '8 dias / 7 noches',
          image:
            'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522469/exercise_1/menorca_pbtaru.jpg',
          discount: '-15%',
        },
      ],
    }
  },
}
</script>
