<template>
  <div class="background-navbar">
    <div class="navbar">
      <div class="navbar--left">
        <NavbarBrand />
        <NavbarSearch />
      </div>
      <div class="navbar--right">
        <Location />
        <Login />
      </div>
    </div>
  </div>
</template>
<style scoped>
.background-navbar {
  width: 100vw;
  background-color: #195590;
}
.navbar {
  width: 100%;
  margin: auto;
  display: flex;
  padding: 0 10px;
  justify-content: space-around;
  align-items: center;
  text-align: center;
}

.navbar--right {
  display: flex;
  flex-grow: 1;
  justify-content: flex-end;
  align-items: center;
  text-align: center;
}

.navbar--right > div {
  border-left: 1px solid #1f66a2;
}

.navbar--left {
  display: flex;
  flex-grow: 2;
  justify-content: space-around;
  align-items: center;
  text-align: center;
}
@media only screen and (min-width: 1200px) {
  .navbar {
    width: 90%;
    justify-content: space-between;
    padding: 0;
  }
  .navbar--left {
    justify-content: space-between;
  }
}

@media only screen and (min-width: 1400px) {
  .navbar {
    width: 70%;
  }
}
</style>
