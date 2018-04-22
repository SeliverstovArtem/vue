<template lang="pug">
  div#app
    header-app
    main-app(:message="msg")
    footer-app
</template>

<script>
import HeaderApp from "./Header-app.vue"
import FooterApp from "./Footer-app.vue"
import MainApp from "./Main-app.vue"
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    HeaderApp,
    FooterApp,
    MainApp
  }
}
</script>

<style lang="sass">
  body, html
    margin: 0
    padding: 0
    min-height: 100vh
    font-family: 'Avenir', Helvetica, Arial, sans-serif
    font-size: 16px

  #app
    -webkit-font-smoothing: antialiased
    -moz-osx-font-smoothing: grayscale
    text-align: center
    color: #2c3e50
    // margin-top: 60px
    display: grid
    grid: "header" 3em "main" auto "footer" 3em
    min-height: 100vh

  h1, h2
    font-weight: normal

  ul
    list-style-type: none
    padding: 0

  li
    display: inline-block
    margin: 0 10px

  a
    color: #42b983
</style>
