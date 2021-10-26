<template>
  <router-view v-slot="{ Component }">
    <transition name="slide-fade">
      <component :is="Component" />
    </transition>
  </router-view>
</template>

<script>
import Logo from './components/Logo.vue'

export default {
  name: 'App',
  components: {
    Logo
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: Dosis;
}

#app {
  font-family: Dosis, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  height: 100vh;
  width: 100vw;
  color: #2c3e50;
  flex-direction: column;
}

a {
  color: #2c3e50;
  font-weight: 800;
  text-decoration: none;
}

.container {
  min-height: 100vh;
  min-width: 100vw;
}

.slide-fade-enter-active {
  transition: all 0.5s ease-out;
}

.slide-fade-leave-active {
  transition: all 0.3s cubic-bezier(1, 0.5, 0.8, 1);
}

.slide-fade-enter-from,
.slide-fade-leave-to {
  transform: translateX(-10%);
  opacity: 0;
}

</style>
