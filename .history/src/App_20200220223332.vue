<template>
  <div id="app" class="small-container">
    <h1>Employees</h1>
  </div>
</template>

<script>
import Empl from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    EmployeeTables
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
