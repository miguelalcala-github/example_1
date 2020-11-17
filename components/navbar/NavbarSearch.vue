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

<style scoped>
.navbar__search {
  background-color: white;
  border: 1px solid #164d80;
  border-radius: 3px;
  display: flex;
}

.navbar__search-icon {
  transform: scaleX(-1);
  padding: 1px 0;
}

.navbar__search-input {
  border: none;
  color: #d5d5d5;
  margin: 0 10px;
  height: 100%;
}

.navbar__search-input::placeholder {
  color: #d5d5d5;
}

.navbar__scope-wrapper {
  position: relative;
  width: 105px;
  display: flex;
  padding: 11px 9px;
  border-right: 1px solid #ebebeb;
}

.navbar__input-wrapper {
  padding-right: 9px;
  display: flex;
  justify-content: center;
}

.navbar__scope-wrapper select {
  -webkit-appearance: none;
  -ms-appearance: none;
  -moz-appearance: none;
  appearance: none;
  background-color: transparent;
  z-index: 1;
  border: none;
  flex-grow: 1;
}

.navbar__scope-wrapper::after {
  content: url('~assets/svg/selectIcon.svg');
  position: absolute;
  top: 28%;
  right: 5px;
  z-index: 0;
}
</style>
