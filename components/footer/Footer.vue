<template>
  <div class="footer text-sm">
    <span>{{ brandInfo }}</span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      brandInfo:
        'Logitravel S.L. - Agencia de viajes on-line con el CI.BAL 471, 2004 - Todos los derechos reservados.',
    }
  },
}
</script>

<style scoped>
.footer {
  width: 100%;
  height: 100px;
  text-align: center;
  background-color: #164e7f;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
}
.footer span {
  color: white;
}
.footer::before {
  content: '';
  width: 100%;
  height: 20px;
  background-color: #195590;
  position: absolute;
  top: 0px;
}
</style>
