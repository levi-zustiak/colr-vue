<template>
  <h1 class="logo">
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
  font-size: 48px;
  font-weight: 800;
  top: 50px;
  left: 50px;
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
