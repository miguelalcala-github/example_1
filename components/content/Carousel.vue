<template>
  <div class="carousel__container">
    <div class="carousel__arrow-left">
      <img
        src="@/assets/svg/selectIcon.svg"
        alt="prev offers"
        @click="goTo(currentPageIndex - 1)"
      />
    </div>

    <CarouselCard
      v-for="(card, index) in cards"
      :key="index"
      :offer="card"
      :class="getClass(currentPageIndex, index)"
    />
    <div class="carousel__arrow-right">
      <img
        src="@/assets/svg/selectIcon.svg"
        alt="next offers"
        @click="goTo(currentPageIndex + 1)"
      />
    </div>
  </div>
</template>

<script>
export default {
  props: {
    currentSection: {
      type: String,
      default: 'destacados',
    },
  },
  async fetch() {
    this.cards = await this.$content('offers')
      .where({ section: { $contains: this.currentSection } })
      .fetch()
  },
  data() {
    return {
      cards: [],
      // cards2: [
      //   {
      //     destination: 'Menorca',
      //     duration: '8 dias / 7 noches',
      //     image:
      //       'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522469/exercise_1/menorca_pbtaru.jpg',
      //     discount: '-15%',
      //     options: [
      //       { type: 'Fly', data: 'Raynair' },
      //       { type: 'Host', data: 'Blue Sea San Anton Hotel & Spa', stars: 3 },
      //       { type: 'Renting', data: 'Fiat 500 o similiar' },
      //     ],
      //     price: 339,
      //     section: ['baleares y canarias', 'mediterraneo', 'destacados'],
      //   },
      //   {
      //     destination: 'Cancun',
      //     duration: '8 dias / 7 noches',
      //     image:
      //       'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522469/exercise_1/cancun_krwpsw.jpg',
      //     discount: '-30%',
      //     special: 'todo incluido',
      //     options: [
      //       { type: 'Fly', data: 'Regular' },
      //       { type: 'Host', data: 'Flamingo Cancun', stars: 4 },
      //       { type: 'Transport', data: 'Traslados aeropuerto - hotel' },
      //     ],
      //     price: 898,
      //     section: ['caribe', 'larga distancia', 'destacados'],
      //   },
      //   {
      //     destination: 'Londres',
      //     duration: '8 dias / 7 noches',
      //     image:
      //       'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522468/exercise_1/londres_pbvkav.jpg',
      //     discount: '-30%',
      //     options: [
      //       { type: 'From', data: 'Barcelona' },
      //       { type: 'Fly', data: 'Raynair' },
      //       { type: 'Renting', data: 'Hotel Lords', stars: 2 },
      //     ],
      //     price: 150,
      //     section: ['capitales europeas', 'destacados'],
      //   },
      //   {
      //     destination: 'Menorca',
      //     duration: '8 dias / 7 noches',
      //     image:
      //       'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522469/exercise_1/menorca_pbtaru.jpg',
      //     discount: '-15%',
      //     options: [
      //       { type: 'Fly', data: 'Raynair' },
      //       { type: 'Host', data: 'Blue Sea San Anton Hotel & Spa', stars: 3 },
      //       { type: 'Renting', data: 'Fiat 500 o similiar' },
      //     ],
      //     price: 339,
      //     section: ['baleares y canarias', 'mediterraneo', 'destacados'],
      //   },
      //   {
      //     destination: 'Mallorca',
      //     duration: '8 dias / 7 noches',
      //     image:
      //       'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522469/exercise_1/menorca_pbtaru.jpg',
      //     discount: '-15%',
      //     options: [
      //       { type: 'Fly', data: 'Raynair' },
      //       { type: 'Host', data: 'Blue Sea San Anton Hotel & Spa', stars: 3 },
      //       { type: 'Renting', data: 'Fiat 500 o similiar' },
      //     ],
      //     price: 339,
      //     section: ['baleares y canarias', 'mediterraneo', 'destacados'],
      //   },
      //   {
      //     destination: 'Cancun',
      //     duration: '8 dias / 7 noches',
      //     image:
      //       'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522469/exercise_1/cancun_krwpsw.jpg',
      //     discount: '-30%',
      //     special: 'todo incluido',
      //     options: [
      //       { type: 'Fly', data: 'Regular' },
      //       { type: 'Host', data: 'Flamingo Cancun', stars: 4 },
      //       { type: 'Transport', data: 'Traslados aeropuerto - hotel' },
      //     ],
      //     price: 898,
      //     section: ['caribe', 'larga distancia', 'destacados'],
      //   },
      //   {
      //     destination: 'Londres',
      //     duration: '8 dias / 7 noches',
      //     image:
      //       'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522468/exercise_1/londres_pbvkav.jpg',
      //     discount: '-30%',
      //     options: [
      //       { type: 'From', data: 'Barcelona' },
      //       { type: 'Fly', data: 'Raynair' },
      //       { type: 'Renting', data: 'Hotel Lords', stars: 2 },
      //     ],
      //     price: 150,
      //     section: ['capitales europeas', 'destacados'],
      //   },
      //   {
      //     destination: 'Mallorca',
      //     duration: '8 dias / 7 noches',
      //     image:
      //       'https://res.cloudinary.com/da3z5stec/image/upload/h_720,w_1280/v1605522469/exercise_1/menorca_pbtaru.jpg',
      //     discount: '-15%',
      //     options: [
      //       { type: 'Fly', data: 'Raynair' },
      //       { type: 'Host', data: 'Blue Sea San Anton Hotel & Spa', stars: 3 },
      //       { type: 'Renting', data: 'Fiat 500 o similiar' },
      //     ],
      //     price: 339,
      //     section: ['baleares y canarias', 'mediterraneo', 'destacados'],
      //   },
      // ],
      currentPageIndex: 0,
      cardsPerPage: 4,
      currentCards: [],
    }
  },
  watch: {
    currentSection: '$fetch',
  },
  // computed: {
  //   currentSectionCards() {
  //     this.generateCurrentSectionCards()
  //     return this.currentCards
  //   },
  // },
  methods: {
    getClass(pageIndex, index) {
      const minIndex = this.cardsPerPage * pageIndex
      const maxIndex = minIndex + this.cardsPerPage

      return { cardShow: !(index >= minIndex && index < maxIndex) }
    },
    goTo(index) {
      if (index >= 0 && this.cardsPerPage * index < this.cards.length) {
        this.currentPageIndex = index
      }
    },
    // generateCurrentSectionCards() {
    //   this.currentCards = this.cards.filter((card) =>
    //     card.section.some((section) => section.includes(this.currentSection))
    //   )
    // },
  },
}
</script>
