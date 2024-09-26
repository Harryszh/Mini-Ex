<template>
    <div class="register">
      <h2>Register</h2>
      <form @submit.prevent="registerUser">
        <div>
          <label for="name">Name:</label>
          <input v-model="form.name" type="text" id="name" required />
        </div>
        <div>
          <label for="email">Email:</label>
          <input v-model="form.email" type="email" id="email" required />
        </div>
        <div>
          <label for="password">Password:</label>
          <input v-model="form.password" type="password" id="password" required />
        </div>
        <div>
          <label for="password_confirmation">Confirm Password:</label>
          <input v-model="form.password_confirmation" type="password" id="password_confirmation" required />
        </div>
        <button type="submit">Register</button>
      </form>
    </div>
  </template>

<script>
import axios from 'axios';

export default {
  data() {
    return {
      form: {
        name: '',
        email: '',
        password: '',
        password_confirmation: ''
      },
      errors: []
    };
  },
  methods: {
    async registerUser() {
      try {
        // Sende die Registrierungsdaten an das Backend (z.B. Laravel API)
        await axios.post('/register', this.form);
        // Nach erfolgreicher Registrierung weiterleiten
        this.$router.push('/login');
      } catch (error) {
        if (error.response && error.response.data.errors) {
          this.errors = error.response.data.errors;
        }
      }
    }
  }
};
