<template>
  <div class="menu">
    <MenuOption  v-for="(color,index) in colors"
      :key="index"
      :option="options[index]"
      :color="color"
    />
  </div>
</template>

<script>
import axios from 'axios'

import MenuOption from '../components/MenuOption.vue'

export default {
  name: 'Index',
  components: {
    MenuOption
  },
  data() {
    return {
      colors: [],
      options: ["Generate", "Explore"]
    }
  },
  methods: {
    random: function () {
      return Math.floor(Math.random()*16777215).toString(16);
    }
  },
  beforeMount() {
    const color = this.random()
    const apiCall = `https://www.thecolorapi.com/scheme?hex=${color}&mode=analogic&count=2`
    axios.get(apiCall)
      .then(res => {
        this.colors = res.data.colors
      })
      .catch(e => {
        this.errors.push(e)
      })
  }
}
</script>

<style scoped>
  .menu {
    height: 100vh;
    width: 100vw;
    display: flex;
  }
</style>
