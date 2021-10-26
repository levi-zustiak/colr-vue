<template>
  <transition name="slide" mode="out-in">
    <div id="generate" class="container">
      <BackButton />
      <Color v-for="(color, index) in colors"
        :key="index"
        :color="color"
      />
      <div class="options">
        <div @click="getColors" class="generate-colors-button no-select">
          <h3>Generate</h3>
        </div>
        <Select
          @change="changeMode($event)"
          :options="modes"
          :selected="mode"
        />
        <Select
          @change="changeNumber($event)"
          :options="number"
          :selected="count"
        />
      </div>
    </div>
  </transition>
</template>

<script>
import axios from 'axios'

import Color from '../components/Color.vue'
import BackButton from '../components/BackButton.vue'
import Select from '../components/Select.vue'

export default {
  name: 'Generate',
  components: {
    Color,
    BackButton,
    Select
  },
  data() {
    return {
      colors: [],
      modes: ['analogic', 'complement', 'analogic-complement', 'monochrome', 'monochrome-dark', 'monochrome-light', 'triad', 'quad'],
      number: [...Array(10).keys()].map(x=>++x).reverse(),
      count: 5,
      mode: 'analogic',
    }
  },
  methods: {
    random: function () {
      return (Math.random() * 0xFFFFFF << 0).toString(16).padStart(6, '0')
    },
    getColors: function () {
      const color = this.random()
      const apiCall = `https://www.thecolorapi.com/scheme?hex=${color}&mode=${this.mode}&count=${this.count}`
      axios.get(apiCall)
        .then(res => {
          this.colors = res.data.colors
        })
        .catch(e => {
          this.errors.push(e)
        })
    },
    changeMode: function(e) {
      this.mode = e.target.value
    },
    changeNumber: function(e) {
      this.count = e.target.value
    }
  },
  beforeMount() {
    this.getColors()
  }
}
</script>

<style scoped>
#generate {
  display: flex;
}

.options {
  position: absolute;
  bottom: 10vh;
  width: 100%;
  padding: 12px;
  display: flex;
  justify-content: center;
  gap: 48px;
}

.generate-colors-button {
  height: 50px;
  width: 125px;
  border: 3px solid white;
  color: white;
  border-radius: 8px;
  transition: .5s;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor:pointer;
}

.generate-colors-button:hover {
  background-color: white;
  color: black
}
</style>
