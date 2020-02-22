<template>
  <div id="employee-table">
    <table>
      <thead>
        <th>Employee name</th>
        <th>Employee email</th>
        <th>Actions</th>
      </thead>
      <tbody>
        <tr v-for="employee in employees" :key="employee.id">
          <td>{{ employee.name }}</td>
          <td>{{ employee.email }}</td>
          <td>
            <button>Edit</button>
            <button class="danger-button">Delete</button>
          </td>
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
button {
  margin: 0 0.5rem 0 0;
}
button .edit-button {
  background-color: blue !important;
}
button .danger-button {
  background-color: rgb(158, 23, 23) !important;
}
</style>