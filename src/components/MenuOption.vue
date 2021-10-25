<template>
  <a href="#" class="option" v-bind:style="{ backgroundColor: color.hex.value, color: color.contrast.value}"> {{ option }} </a>
</template>


<script>
export default {
  name: 'MenuOption',
  props: {
    option: String,
    color: Object
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
