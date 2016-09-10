<template>
  {{ name }}
  <button @click="removeMenu(index)">x</button>
</template>

<script>
export default {
  props: ['name', 'removeMenu', 'index']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
</style>
