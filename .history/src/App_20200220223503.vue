<template>
  <div id="app" class="small-container">
    <h1>Employees</h1><employee-table/ />
  </div>
</template>

<script>
import EmployeeTable from "@/components/EmployeeTable.vue";

export default {
  name: "app",
  components: {
    EmployeeTable
  }
};
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
