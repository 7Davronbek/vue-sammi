<template>
  <div class="MovieList py-4">
    <div class="container">
      <div class="row">
        <div class="col-10 mx-auto">
          <MovieListItem />
          <MovieListItem />
          <MovieListItem />
          <MovieListItem />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import MovieListItem from '../movie-list-item/MovieListItem.vue'

export default {
  components: {
    MovieListItem
  }
}
</script>

<style></style>
