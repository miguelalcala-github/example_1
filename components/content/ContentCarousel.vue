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
    <Carousel />
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
      optionSelected: null,
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
