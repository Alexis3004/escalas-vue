<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <hallazgos-memoria></hallazgos-memoria>
  <habla-lenguaje></habla-lenguaje>
</template>

<script>
import HallazgosMemoria from './components/HallazgosMemoria.vue'
import HablaLenguaje from './components/HablaLenguaje.vue'

export default {
  name: 'App',
  components: {
    HallazgosMemoria,
    HablaLenguaje
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
