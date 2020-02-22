<template>
  <div id="employee-table">
    <table>
      <thead>
        <th>Employee name</th>
        <th>Employee email</th>
      </thead>
      <tbody>
        <tr v-for="employee in employees" :key="employee.id">
          <td>{{ employee.name }}</td>
          <td>richard@piedpiper.com</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: "employee-table",
  props: {
    employees: Array
  }
};
</script>

<style scoped>
</style>