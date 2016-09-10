<template>
  <form @submit.prevent="addMenu(inputMenu)">
    <input :value="inputMenu" @input="onInput($event)">
    <input type="submit" value="add">
  </form>
</template>

<script>
export default {
  props: ['inputMenu', 'addMenu', 'onInput']
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
</style>
