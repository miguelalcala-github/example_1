<template>
  <div class="carousel__col">
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

<style scoped>
.card {
  border-radius: 5px;
  overflow: hidden;
  box-shadow: 0px 2px 2px -2px lightslategrey;
}

.card__body {
  border-right: 1px solid #e8e8e8;
  border-left: 1px solid #e8e8e8;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: flex-start;
  padding: 9px;
}

.card__discount {
  content: '';
  position: absolute;
  top: -40px;
  right: -40px;
  background-color: red;
  width: 80px;
  height: 80px;
  transform: rotate(45deg);
}

.card__discount p {
  position: absolute;
  width: 100%;
  text-align: center;
  bottom: 5px;
}

.card__footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 7px;
  border: 1px solid #e8e8e8;
  border-radius: 0px 0px 5px 5px;
}

.card__footer a {
  text-decoration: none;
  text-transform: uppercase;
  color: white;
  background-color: goldenrod;
  padding: 7px 25px;
  border-radius: 5px;
}

.card__footer-price {
  color: goldenrod;
}

.card__head {
  display: flex;
  position: relative;
  color: #fff;
}

.card__image {
  border-radius: 5px 5px 0 0;
  width: 100%;
}

.card__offer {
  position: absolute;
  bottom: 5px;
  left: 0px;
  padding: 12px 7px;
}

.card__offer span {
  display: inline-block;
  background-color: red;
  font-size: small;
  text-transform: uppercase;
  border-radius: 10px;
  padding: 1px 7px;
  margin-left: 2px;
}

.card__offer span::after {
  content: '';
  background-color: red;
  border-radius: 50%;
}

.carousel__col {
  width: 25%;
  padding: 0px 6px;
}
</style>
