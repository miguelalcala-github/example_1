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
      :class="getClass(index, card)"
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
    this.currentPageIndex = 0
    this.cards = await this.$content('offers')
      .where({ section: { $contains: this.currentSection } })
      .fetch()
  },
  data() {
    return {
      cards: [],
      currentPageIndex: 0,
      prevPageIndex: 0,
      cardsPerPage: 4,
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
    getClass(index, card) {
      const minIndex = this.cardsPerPage * this.currentPageIndex
      const maxIndex = minIndex + this.cardsPerPage
      return {
        cardHide: !(index >= minIndex && index < maxIndex),
      }
    },
    goTo(pageIndex) {
      if (pageIndex >= 0 && this.cardsPerPage * pageIndex < this.cards.length) {
        this.currentPageIndex = pageIndex
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

<style scoped>
.carousel__arrow-right {
  position: absolute;
  right: -35px;
  transform: rotate(-90deg);
}
.carousel__arrow-right img {
  width: 40px;
}
.carousel__arrow-left {
  position: absolute;
  left: -35px;
  transform: rotate(90deg);
}
.carousel__arrow-left img {
  width: 40px;
}

.carousel__container {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: flex-start;
  padding: 12px 0;
  position: relative;
}
</style>
