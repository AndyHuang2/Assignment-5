<script setup>
import { useRoute, useRouter } from "vue-router";
import Details from "../components/Details.vue";

const route = useRoute();
const router = useRouter();
const movieId = route.params.id;

if (!movieId) {
  router.push("/"); // Redirect if no movie ID is found
}
</script>

<template>
  <div class="details-view">
    <Details :id="movieId" />
    <button @click="router.push('/')">Back to Movies</button>
  </div>
</template>

<style scoped></style>
