<script setup>
import { ref } from 'vue';
import { useRouter } from 'vue-router';
const router = useRouter();
const password = ref('')
const password2 = ref('')
function handleSubmit() {
  if (password.value === password2.value) {
    router.push("/login");
  } else {
    window.alert("The passwords are not the same!");
  }
}
</script>

<template>
  <div class="hero">
    <div class="overlay">
      <div class="navbar">
        <h1>NotNetflix</h1>
      </div>
      <div class="form-container">
        <h2>Register</h2>
        <form @submit.prevent="handleSubmit">
          <input type="First Name" placeholder="First Name" class="input-field" required />
          <input type="Last Name" placeholder="Last Name" class="input-field" required />
          <input type="Email" placeholder="Email" class="input-field" required />
          <input v-model="password" type="Password" placeholder="Password" class="input-field" required />
          <input v-model="password2" type="Password" placeholder="Comfirm Password" class="input-field" required />
          <button type="submit" class="button register">Register</button>
        </form>
      </div>
    </div>
  </div>
</template>

<style scoped>
body {
  background-color: #121212;
  color: #e0e0e0;
  font-family: Arial, sans-serif;
  margin: 0;
  padding: 0;
}

.hero {
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
  width: 100%;
  background-color: #1d1d1d;
  position: relative;
}

.overlay {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  justify-content: center;
  align-items: center;
}

.navbar {
  position: absolute;
  top: 20px;
  left: 20px;
  right: 20px;
  display: flex;
  justify-content: space-between;
  z-index: 10;
}

.navbar h1 {
  font-size: 32px;
  color: #ffffff;
  margin: 0;
}

.button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  background-color: #001aff;
  color: white;
  transition: background-color 0.3s;
}

.button:hover {
  background-color: #001aff;
}

.register {
  margin-left: auto;
}

.form-container {
  background-color: #333333;
  padding: 40px;
  border-radius: 10px;
  width: 400px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
  z-index: 10;
}

.form-container h2 {
  margin-bottom: 20px;
  font-size: 24px;
  color: #ffffff;
}

.input-field {
  width: 100%;
  padding: 15px;
  margin-bottom: 20px;
  border: 1px solid #444;
  background-color: #222;
  color: #fff;
  border-radius: 5px;
}

.input-field:focus {
  outline: none;
  border-color: #001aff;
}

.register {
  background-color: #001aff;
  width: 100%;
  padding: 15px;
}

.register:hover {
  background-color: #425efc;
}
</style>