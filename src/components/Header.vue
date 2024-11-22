<script setup>
</script>
<template>
    <div class = header>
        <h1>NotNetflix</h1>
    </div>
    <div class="buttons">
            <button>sign in</button>
            <button>sign up</button>
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
    width: auto;
}

button {
    margin: 10px;
    padding: 15px 20px;
    background-color: darkgray;

}

.buttons {
    display: flex;
    justify-content: center;
}
</style>