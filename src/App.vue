<template>
  <div id="app">
    <h1>Call components:</h1>
    <Test msg="Hola hijo!!!"/>
  </div>
</template>

<script>
import Test from './components/Test.vue';

export default {
  name: 'App',
  components: {
    Test
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
