<template>
  <div class="card__option text-sm">
    <img :src="srcType" :alt="option.type" />
    <span
      ><p v-if="option.type === 'Fly'">
        Vuelo <b>{{ option.data }}</b>
      </p>
      <p v-else-if="option.type === 'From'">
        <b>Desde {{ option.data }}</b>
      </p>
      <p v-else>
        {{ option.data }}
        <img
          v-for="n in option.stars"
          v-show="option.stars"
          :key="n"
          src="@/assets/svg/icon-Star.svg"
          alt="hotel rank"
          class="card__option-star"
        /></p
    ></span>
  </div>
</template>
<script>
export default {
  props: {
    option: {
      type: Object,
      required: true,
    },
  },
  computed: {
    srcType() {
      return require(`@/assets/svg/icon-${this.option.type}.svg`)
    },
  },
}
</script>
<style scoped>
.card__option {
  display: flex;
  flex-wrap: nowrap;
  padding: 2px 0;
}

.card__option > img {
  width: 15px;
  height: 15px;
  margin-right: 9px;
}

.card__option-star {
  width: 10px;
  height: 10px;
}
</style>
