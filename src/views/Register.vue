<script setup>
</script>
<template>
  <div class="hero">
    <div class="overlay">
      <div class="navbar">
        <h1>NotNetflix</h1>
      </div>
      <div class="form-container">
        <h2>Register</h2>
        <form>
          <input type="First Name" placeholder="First Name" class="input-field" required />
          <input type="Last Name" placeholder="Last Name" class="input-field" required />
          <input type="Email" placeholder="Email" class="input-field" required />
          <input type="Password" placeholder="Password" class="input-field" required />
          <input type="Confirm Password" placeholder="Password" class="input-field" required />
          <button type="button" class="button login">Register</button>
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
  justify-content: space-between; /* Push logo to the left, register button to the right */
  z-index: 10;
}

.navbar h1 {
  font-size: 32px;
  color: #ffffff;
  margin: 0; /* Remove default margin */
}

.button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  background-color: #6200ea;
  color: white;
  transition: background-color 0.3s;
}

.button:hover {
  background-color: #3700b3;
}

.register {
  margin-left: auto; /* Ensures the register button stays on the right */
}

.form-container {
  background-color: #333333;
  padding: 40px; /* Increased padding for a bigger form */
  border-radius: 10px;
  width: 400px; /* Increased width */
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
  padding: 15px; /* Increased padding for larger inputs */
  margin-bottom: 20px; /* Increased margin between inputs */
  border: 1px solid #444;
  background-color: #222;
  color: #fff;
  border-radius: 5px;
}

.input-field:focus {
  outline: none;
  border-color: #6200ea;
}

.login {
  background-color: #03dac5;
  width: 100%; /* Ensure the login button is full width */
  padding: 15px; /* Increased padding for a bigger button */
}

.login:hover {
  background-color: #018786;
}

</style>