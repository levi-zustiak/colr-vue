<template>
  <h1 class="logo no-select">
    <span class="C">C</span>
    <span class="o">o</span>
    <span class="l">l</span>
    <span class="r">r</span>
  </h1>
</template>

<script>
export default {
  name: 'Logo'
}
</script>

<style scoped>
.logo {
  position: absolute;
  top: 65px;
  left: 65px;
  font-size: 48px;
  font-weight: 800;
  border-radius: 8px;
  padding: 0px 10px;
}

.C {
  color: #FF5E5B;
}

.o {
  color: #FFFFEA;
}

.l {
  color: #FFED66;
}

.r {
  color: #00CECB;
}
</style>
