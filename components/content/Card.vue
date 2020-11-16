<template>
  <div class="card">
    <div class="card__head">
      <img :src="offer.image" :alt="offer.destination" class="card__image" />
      <div class="card__offer">
        <h3>{{ offer.destination }}</h3>
        <p class="text-sm">
          {{ offer.duration }}
          <span v-show="offer.special">{{ offer.special }}</span>
        </p>
      </div>
      <div v-show="offer.discount" class="card__discount">
        <p class="text-md">{{ offer.discount }}</p>
      </div>
    </div>
    <div class="card__body">
      <Option
        v-for="option in offer.options"
        :key="option.type"
        :option="option"
      />
    </div>
    <div class="card__footer">
      <div class="card__footer-price">
        <p class="text-sm">desde</p>
        <p>{{ offer.price }} €</p>
      </div>
      <nuxt-link to="#">reservar</nuxt-link>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    offer: {
      type: Object,
      required: true,
    },
  },
}
</script>
