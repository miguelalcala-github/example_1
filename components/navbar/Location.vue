<template>
  <div class="navbar__location">
    <img src="@/assets/svg/locationIcon.svg" />
    <div class="navbar__location-user">
      <p class="text-sm text-nowrap">Mi origen es</p>
      <p class="text-md">{{ location }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      location: '',
    }
  },
  beforeMount() {
    if ('geolocation' in navigator) {
      navigator.geolocation.getCurrentPosition((position) => {
        const latlng = {
          lat: parseFloat(position.coords.latitude),
          lng: parseFloat(position.coords.longitude),
        }

        this.reverseGeolocation(latlng)
      })
    } else {
      alert('Sorry We can give you all utilities without activate geolocation.')
    }
  },

  methods: {
    async reverseGeolocation(latlng) {
      this.location = await fetch(
        `https://nominatim.openstreetmap.org/reverse?format=jsonv2&lat=${latlng.lat}&lon=${latlng.lng}`
      )
        .then((response) => {
          if (response.status === 200) {
            return response.json()
          } else {
            console.log(
              'Looks like there was a problem. Status Code: ' + response.status
            )
            return 'World'
          }
        })
        .then((data) => data.address.city)
        .catch((e) => console.log('Error Fetching Location :-S', e))
    },
  },
}
</script>

<style scoped>
.navbar__location {
  display: flex;
  justify-content: center;
  color: white;
  padding: 10px;
}

.navbar__location-user {
  margin-left: 10px;
}
</style>
