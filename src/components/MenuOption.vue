<template>
  <router-link
    v-if="color.hex"
    :to="route"
    class="option"
    v-bind:style="{
      backgroundColor: color.hex.value,
      color: color.contrast.value
    }"
  >
    {{label}}
  </router-link>
</template>


<script>
export default {
  name: 'MenuOption',
  props: {
    color: Object,
    label: String,
    route: String
  }
}
</script>

<style scoped>
  .option {
    height: 100%;
    width: 100%;
    display: flex;
    align-items: center;
    justify-content: center;
    font-size: 64px;
  }
</style>
