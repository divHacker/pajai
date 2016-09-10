<template>
  <div id="app">
    <app-header></app-header>
    <menus :menus="menus" :remove-menu="removeMenu"></menus>
    <new-menu :input-menu="inputMenu" :add-menu="addMenu" :on-input="onInput"></new-menu>
  </div>
</template>

<script>
import AppHeader from './components/AppHeader'
import Menus from './components/Menus'
import NewMenu from './components/NewMenu'

export default {
  components: {
    AppHeader,
    Menus,
    NewMenu
  },
  data () {
    return {
      inputMenu: '',
      menus: [
        {
          name: 'สุกี้น้ำ'
        },
        {
          name: 'คั่วกลิ้ง'
        }
      ]
    }
  },
  methods: {
    addMenu (name) {
      name = name.trim()
      let isMenuExist = this.menus.find(function (menu) {
        return menu.name === name
      })
      if (name !== '' && !isMenuExist) {
        let newMenu = { name }
        this.menus.push(newMenu)
        this.inputMenu = ''
      }
    },
    removeMenu (index) {
      this.menus.splice(index, 1)
    },
    onInput (e) {
      this.inputMenu = e.target.value
    }
  }
}
</script>

<style>
html {
  height: 100%;
}

body {
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100%;
}

#app {
  color: #2c3e50;
  margin-top: -100px;
  max-width: 600px;
  font-family: Source Sans Pro, Helvetica, sans-serif;
  text-align: center;
}

#app a {
  color: #42b983;
  text-decoration: none;
}

.logo {
  width: 100px;
  height: 100px
}
</style>
