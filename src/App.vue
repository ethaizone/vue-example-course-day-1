<template>
  <div id="app">
    <sidebar v-bind:items="sidebar.items"></sidebar>
    <search-box></search-box>
    <web-content></web-content>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar'
import WebContent from './components/WebContent'
import SearchBox from './components/SearchBox'

export default {
  name: 'app',
  data () {
    return {
      sidebar: {
        items: ['menu1', 'menu2', 'menu3']
      }
    }
  },
  components: {
    WebContent,
    Sidebar,
    SearchBox
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
