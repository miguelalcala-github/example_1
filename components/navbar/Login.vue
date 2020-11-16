<template>
  <div class="navbar__login">
    <img src="@/assets/svg/loginIcon.svg" />
    <div class="navbar__login-user">
      <p class="text-nowrap text-sm">Hola, accede a</p>
      <div class="dropdown" @click="toggleLogin">
        <span>
          <p class="text-nowrap text-md">{{ loginInfo }}</p>
          <img
            v-if="!showDropdownContent"
            class="util--angle"
            src="@/assets/svg/angleDownIcon.svg"
          />
          <img v-else class="util--angle" src="@/assets/svg/angleUpIcon.svg" />
        </span>
        <div v-if="showDropdownContent" class="dropdown-content text-md">
          <nuxt-link v-for="(link, index) in links" :key="index" to="#">{{
            link
          }}</nuxt-link>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      loginInfo: 'Mi cuenta',
      showDropdownContent: false,
      links: ['Sign in', 'Sign up', 'Locations'],
    }
  },
  methods: {
    toggleLogin() {
      this.showDropdownContent = !this.showDropdownContent
    },
  },
}
</script>
