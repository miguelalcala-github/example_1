<template>
  <div>
    <ul class="carousel__header text-sm text-gray">
      <li
        v-for="(option, index) in options"
        :key="index"
        :class="getClass(option)"
        @click="selectOption(option)"
      >
        {{ option }}
      </li>
    </ul>
    <Carousel :current-section="optionSelected" />
  </div>
</template>

<script>
export default {
  data() {
    return {
      options: [
        'destacados',
        'baleares y canarias',
        'caribe',
        'capitales europeas',
        'mediterraneo',
        'larga distancia',
      ],
      optionSelected: 'destacados',
    }
  },
  methods: {
    selectOption(option) {
      this.optionSelected = option
    },
    getClass(option) {
      return { selected: this.optionSelected === option }
    },
  },
}
</script>

<style scoped>
.carousel__header {
  border-bottom: solid #e8e8e8 1px;
  padding: 0 12px;
}

.carousel__header li {
  display: inline-block;
  padding: 12px;
  text-transform: uppercase;
  position: relative;
  cursor: pointer;
}

.carousel__header li.selected {
  color: black;
}

.carousel__header li.selected::after {
  content: '';
  width: 100%;
  height: 3px;
  background-color: blue;
  bottom: 0px;
  left: 0px;
  position: absolute;
}
</style>
