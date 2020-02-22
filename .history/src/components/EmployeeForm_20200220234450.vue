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
        submitting: false,
        
      employee: {
        name: "",
        email: ""
      }
    };
  },

  methods: {
    handleSubmit() {
      this.$emit("add:addEmployee", this.employee);
    }
  },
  computed: {
    invalideName() {
      return this.employee.name === "";
    },

    invalidEmail() {
      return this.employee.email === "";
    }
  }
};
</script>

<style scoped>
form {
  margin-bottom: 2rem;
}
</style>