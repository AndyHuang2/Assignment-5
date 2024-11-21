<script setup>
</script>
<template> 
    <div class="Hero-section">
        <div class="text">
            <p>Welcome to NotNetflix</p>
        </div>

        <button class="herobuttons">Browse Movies</button>
        <button class="herobuttons2">Trending Movies</button>
    </div>
</template>
<style scoped>
.Hero-section {
    position: relative;
    color: white;
}
.text {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 55px;
    font-family: "Bebas Neue", sans-serif;
    font-weight: 400;
    font-style: normal;
}
.Hero {
    width: 100%;
}
</style>