<script>
import MovieListItem from '../movie-list-item/MovieListItem.vue'

export default {
  components: {
    MovieListItem
  },
  props: {
    movies: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <div class="MovieList py-4">
    <div class="container">
      <div class="row">
        <div class="col-10 mx-auto">
          <MovieListItem
            v-for="movie in movies"
            :key="movie.id"
            :movie="movie"
            @onLike="$emit('onLike', movie.id)"
          />
        </div>
      </div>
    </div>
  </div>
</template>

<style></style>
