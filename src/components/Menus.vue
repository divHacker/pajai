<template>
  <div v-for="menu in menus">
    <menu :name="menu.name" :remove-menu="removeMenu" :index="$index"></menu>
  </div>
</template>

<script>
import Menu from './Menu'
export default {
  props: ['menus', 'removeMenu'],
  components: {
    Menu
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1 {
  color: #42b983;
}
</style>
