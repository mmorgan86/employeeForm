<template>
  <div id="employeeForm">
    <form @submit.prevent="handleSubmit">
      <label>Name</label>
      <input type="text" value="Name" v-model="employee.name" :class="{ 'has-error' : submitting "/>
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
      error: false,
      success: false,
      employee: {
        name: "",
        email: ""
      }
    };
  },

  methods: {
    handleSubmit() {
      this.submitting = true;
      this.clearStatus();

      if (this.invalidName || this.invalidEmail) {
        this.error = true;
        return;
      }

      this.$emit("add:addEmployee", this.employee);
      this.employee = {
        name: "",
        email: ""
      };
      (this.error = false), (this.success = true), (this.submitting = false);
    },

    clearStatus() {
      this.success = false;
      this.error = false;
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

[class*="-message"] {
  font-weight: 500;
}

.error-message {
  color: #d33c40;
}

.success-message {
  color: #32a95d;
}
</style>