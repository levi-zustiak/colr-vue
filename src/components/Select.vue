<template>
  <select>
    <option v-for="option in options" :key="option">
      {{option}}
    </option>
  </select>
</template>

<script>
export default {
  props: {
    options: []
  }
}

</script>

<style scoped>
select {
  border: 3px solid white;
  background-color: transparent;
  border-radius: 8px;
  padding: 10px 15px;
  color: white;
  font-family: Dosis;
  font-weight: 800;
  font-size: 18px;
  transition: .5s;
}

select:hover {
  color: black;
  background-color: white;
}
</style>
