<template>
  <div v-if="movie">
    <h1>{{ movie.title }}</h1>
    <p>{{ movie.overview }}</p>
    <ul>
      <li>Release Date: {{ movie.release_date }}</li>
      <li>Runtime: {{ movie.runtime }} minutes</li>
      <li>Genres: {{ movie.genres.map(genre => genre.name).join(', ') }}</li>
      <li>Rating: {{ movie.vote_average }}</li>
      <li>Budget: ${{ movie.budget.toLocaleString() }}</li>
      <li>Revenue: ${{ movie.revenue.toLocaleString() }}</li>
      <li>Production Companies: {{ movie.production_companies.map(company => company.name).join(', ') }}</li>
    </ul>
  </div>
</template> 
<script setup>
import { ref, onMounted } from 'vue';
import axios from 'axios';
import { useRoute } from 'vue-router';
const route = useRoute();
const movie = ref(null);
async function fetchMovieDetails() {
  const movieId = route.params.id;
  const response = await axios.get(`https://api.themoviedb.org/3/movie/${movieId}?api_key=${import.meta.env.VITE_API_KEY}`);
  movie.value = response.data;
} onMounted(fetchMovieDetails);

<style scoped>
</style>