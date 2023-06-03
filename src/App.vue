<template>
  <CalculadoraTeste msg="CALCULADORA"/>
</template>

<script>
import CalculadoraTeste from './components/CalculadoraTeste.vue'

export default {
  name: 'App',
  components: {
    CalculadoraTeste
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
