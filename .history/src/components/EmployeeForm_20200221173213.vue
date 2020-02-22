<template>
  <div id="employeeForm">
    <form @submit.prevent="handleSubmit">
      <label>Name</label>
      <input
        type="text"
        placeholder="Enter name"
        v-model="employee.name"
        :class="{ 'has-error' : 'submitting && invalidName'}"
        @focus="clearStatus"
        @keydown="clearStatus"
      />
      <label>Email</label>
      <input
        type="text"
        placeholder="Enter email"
        v-model="employee.email"
        :class="{'has-error' : 'submitting && invalidEmail'}"
        @focus="clearStatus"
      />
      <p v-if="error && submitting" class="error-message">!Please fill out all required fields</p>
      <p v-if="success" class="success-message">Employee successfully added</p>
      <button>Add Employee</button>
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

      this.$emit("add:employee", this.employee);
      this.employee = {
        name: "",
        email: ""
      };
      this.error = false;
      this.success = true;
      this.submitting = false;
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