<template>
  <div class="card">
    <div class="card__head">
      <img :src="offer.image" :alt="offer.destination" class="card__image" />
      <div class="card__offer">
        <h3>{{ offer.destination }}</h3>
        <p class="text-sm">{{ offer.duration }}</p>
      </div>
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
