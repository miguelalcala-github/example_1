<template>
  <div>
    <form class="navbar__search" action="#" method="get">
      <div class="navbar__scope-wrapper">
        <select id="search-scope" name="search-scope" class="text-gray">
          <option value="all">Toda la web</option>
        </select>
      </div>
      <div class="navbar__input-wrapper">
        <input
          name="q"
          type="text"
          class="navbar__search-input"
          size="39"
          placeholder="Introduce un destino, ciudad, hotel,..."
        />
        <img src="@/assets/svg/searchIcon.svg" class="navbar__search-icon" />
      </div>
    </form>
  </div>
</template>

<script>
export default {}
</script>
