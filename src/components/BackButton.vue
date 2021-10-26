<template>
  <div class="back-button" @click="goBack">
    <h4 class="no-select">Go back</h4>
  </div>
</template>

<script>
export default {
  methods: {
    goBack() {
      return this.$router.go(-1);
    }
  }
}
</script>

<style scoped>
.back-button {
  position: absolute;
  top: 75px;
  left: 75px;
  border: 2.5px solid white;
  border-radius: 8px;
  padding: 10px 15px;
  transition: .5s;
  color: white;
  cursor: pointer;
}

.back-button h4 {
  font-weight: 800;
  font-size: 18px;
}

.back-button:hover {
  background-color: white;
  color: black;
}
</style>
