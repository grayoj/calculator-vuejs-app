<template>
  <div id="app">
    <navigation></navigation>
    <calculator></calculator>
  </div>
</template>

<script>
import Calculator from './components/Calculator.vue'
import Navigation from './components/Navigation.vue'

export default {
  name: 'App',
  components: {
    Calculator,
    Navigation,
  }
}
</script>

<style>

</style>
