<template>
  <div id="employee-table">
    <p v-if>No Employees</p>
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
            <button class="edit-button">Edit</button>
            <button class="danger-button" @click="$emit('delete:employee', employee.id)">Delete</button>
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

button.edit-button {
  background-color: #2626ff;
  border: 1px solid #2626ff;
}
button.danger-button {
  background-color: rgba(216, 7, 5, 1);
  border: 1px solid rgba(216, 7, 5, 1);
}
</style>