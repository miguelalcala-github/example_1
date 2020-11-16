<template>
  <div class="content-header__container">
    <div class="content-header__left">
      <img src="@/assets/svg/suitcaseIcon.svg" alt="Suitcase Icon" />
      <div class="content-header__offer">
        <h2>Paquetes Vuelo + Hotel</h2>
        <div class="text-sm text-nowrap">
          <p class="text-gray">Tus vacaciones con un <b>15% Descuento...</b></p>
          <div class="dropdown" @click="toggleDropdown">
            <span>
              <p class="text-link text-nowrap">desde {{ origin }}</p>
              <img
                v-if="!showDropdownContent"
                class="util--angle"
                src="@/assets/svg/originDownIcon.svg"
              />
              <img
                v-else
                class="util--angle"
                src="@/assets/svg/originUpIcon.svg"
              />
            </span>
            <div v-if="showDropdownContent" class="dropdown-content text-sm">
              <nuxt-link v-for="(link, index) in links" :key="index" to="#">{{
                link
              }}</nuxt-link>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="content-header__right text-sm text-nowrap">
      <div class="content-header__example">
        <nuxt-link :to="example.link">{{ example.title }}</nuxt-link>
        <p class="text-nowrap text-sm text-gray">
          {{ example.info }} <b>por solo {{ example.price }} €</b>
        </p>
      </div>
      <img :src="example.image" :alt="example.title" class="img--avatar" />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      origin: 'Madrid',
      showDropdownContent: false,
      links: ['Barcelona', 'Malaga', 'Santander'],
      example: {
        link: '#',
        title: 'Pedro y Raquel viajaran a Budapest',
        info: 'Vuelo + Hotel, 5 dias / 4 noches',
        price: 295,
        image:
          'https://www.wallpapertip.com/wmimgs/6-62828_cute-couple-profile-pictures-for-facebook.jpg',
      },
    }
  },
  methods: {
    toggleDropdown() {
      this.showDropdownContent = !this.showDropdownContent
    },
  },
}
</script>
