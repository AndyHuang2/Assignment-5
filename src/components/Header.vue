<script setup>
</script>
<template>
    <div class = header>
        <h1>NotNetflix</h1>
    </div>
    <div class="buttons">
        <RouterLink to="/register" class="button">Register</RouterLink>
        <RouterLink to="/login" class="button">Login</RouterLink>
    </div>
</template>
<style scoped>
h1 {
    color: white;
    text-align: center;
    font-size: 50px;
}

.header {
    font-family: Georgia, 'Times New Roman', Times, serif;
    font-weight: 400;
    font-style: italic;
    background-color: black;
    text-align: center;
    width: 100%;
    padding: 20px 0; /* Adds some padding for the header */
}

.buttons {
    display: flex;
    justify-content: center;
    background-color: black; /* Ensure the button container has the same background as the header */
    padding: 20px 0; /* Add padding to space out the buttons from the header */
}

.button {
    padding: 10px 20px;
    margin: 0 10px; /* Spacing between buttons */
    background-color: #333; /* Dark background for the buttons */
    color: white;
    text-decoration: none;
    border-radius: 5px;
    font-size: 16px;
    transition: background-color 0.3s ease;
}

.button:hover {
    background-color: #555; /* Slightly lighter dark color on hover */
}
</style>