<script>
export default {
  props: {
    moviesCount: {
      type: Number,
      required: true
    },
    favoriteCount: {
      type: Number,
      required: true
    }
  }
}
</script>

<template>
  <h1>All movies: {{ moviesCount }}</h1>
  <h2>Favorite: {{ favoriteCount }}</h2>
</template>

<style scoped>

</style>