<script setup>
import axios from "axios";
import { ref, onMounted, watch } from "vue";

const props = defineProps({
  id: {
    type: String,
    required: true,
  },
});

const movieDetails = ref(null);

async function fetchMovieDetails(id) {
  if (!id) return;

  try {
    const response = await axios.get(
      `https://api.themoviedb.org/3/movie/${id}?api_key=${import.meta.env.VITE_API_KEY}`
    );
    movieDetails.value = response.data;
  } catch (error) {
    console.error("Error fetching movie details:", error);
  }
}

// Fetch details when the component is mounted or the `id` prop changes
onMounted(() => fetchMovieDetails(props.id));
watch(() => props.id, (newId) => fetchMovieDetails(newId));
</script>

<template>
  <div class="details-component">
    <div v-if="movieDetails">
      <img
        :src="`https://image.tmdb.org/t/p/w500${movieDetails.poster_path}`"
        :alt="movieDetails.title"
        class="movie-poster"
      />
      <div class="details-content">
        <h1>{{ movieDetails.title }}</h1>
        <p>Overview: {{ movieDetails.overview }}</p>
        <p>Release Date: {{ movieDetails.release_date }}</p>
        <p>Rating: {{ movieDetails.vote_average }}/10</p>
        <p>Genres:
          <span v-for="genre in movieDetails.genres" :key="genre.id">
            {{ genre.name }}
          </span>
        </p>
        <p>Runtime: {{ movieDetails.runtime }} minutes</p>
      </div>
    </div>
    <div v-else>
      <p>Movie details not found.</p>
    </div>
  </div>
</template>
<style scoped>
</style>