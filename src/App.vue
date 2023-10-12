<template>
  <div id="app">
    <exampleForm msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
import exampleForm from './components/exampleForm.vue'

export default {
  name: 'App',
  components: {
    exampleForm
  }
}
</script>

<style>
body{
  background-color: #000 !important;
  margin: 0;
  display: flex;
  justify-content: center;
  align-items: center;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  background-color: #fff;
  width: 520px !important;
  border-radius: 20px;
}
</style>
