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

  const response = await axios.get(
    `https://api.themoviedb.org/3/movie/${id}?api_key=${import.meta.env.VITE_API_KEY}`
  );
  movieDetails.value = response.data;
}

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
  </div>
</template>
<style scoped>
.details-component {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100vh;
  background-color: #121212;
  color: #e0e0e0;
  font-family: 'Arial', sans-serif;
  padding: 20px;
}

.details-content {
  max-width: 600px;
  margin-left: 20px;
  text-align: left;
  background-color: #1c1c1c;
  border-radius: 12px;
  padding: 20px;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.6);
}

.movie-poster {
  width: 300px;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.8);
}

h1 {
  font-size: 2rem;
  margin: 0;
  color: #fff;
  font-weight: bold;
}

p {
  margin: 10px 0;
  line-height: 1.6;
}

p span {
  margin-right: 10px;
  background-color: #333;
  padding: 5px 8px;
  border-radius: 6px;
  font-size: 0.9rem;
  color: #fff;
}

p span:hover {
  background-color: #6200ea;
}

.details-content p {
  font-size: 1rem;
}

.details-content p:last-child {
  margin-bottom: 0;
}

.details-content h2 {
  font-size: 1.2rem;
  margin-top: 20px;
  color: #bbb;
}

.details-content .rating {
  display: flex;
  align-items: center;
}

.details-content .rating span {
  background-color: #6200ea;
  padding: 5px 8px;
  border-radius: 6px;
  color: #fff;
  font-weight: bold;
  margin-left: 10px;
}
</style>