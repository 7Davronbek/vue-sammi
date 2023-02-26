<template>
  <div class="AppInfo py-4">
    <div class="container">
      <div class="row">
        <div class="col-lg-10 mx-auto">
          <h4>All movies: {{ allMoviesCount }}</h4>
          <h4>Favorite movies: {{ favorite }}</h4>
          <h4>Liked movies: {{ like }}</h4>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    allMoviesCount: {
      type: Number,
      required: true
    },
    favorite: {
      type: Number,
      required: true
    },
    like: {
      type: Number,
      required: true
    }
  }
}
</script>

<style></style>
