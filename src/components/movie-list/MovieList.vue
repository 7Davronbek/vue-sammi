<script>
import MovieListItem from '../movie-list-item/MovieListItem.vue'

export default {
  components: {
    MovieListItem
  },
  data() {
    return {
      movies: [
        {
          name: 'Omar',
          viewers: 204,
          like: true,
          favorite: true
        },
        {
          name: 'Golder',
          viewers: 463,
          like: false,
          favorite: false
        },
        {
          name: "Truman's show",
          viewers: 998,
          like: false,
          favorite: true
        }
      ]
    }
  }
}
</script>

<template>
  <div class="MovieList py-4">
    <div class="container">
      <div class="row">
        <div class="col-10 mx-auto">
          <MovieListItem v-for="movie in movies" :key="movie.name" :movie="movie" />
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>
