<template>
  <div id="employeeForm">
    <form @submit.prevent="handleSubmit">
      <label>Name</label>
      <input type="text" value="Name" v-model="employee.name" />
      <label>Email</label>
      <input type="text" value="Email" v-model="employee.email" />
      <button>Submit</button>
    </form>
  </div>
</template>

<script>
export default {
  name: "employee-form",
  data() {
    return {
      employee: {
        name: "",
        email: ""
      }
    };
  },

  methods: {
      onSubmit() {
          this.$emit
      }
  }
};
</script>

<style>
</style>