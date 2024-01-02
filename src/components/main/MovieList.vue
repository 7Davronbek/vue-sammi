<script>

import SingleMovie from '@/components/main/SingleMovie.vue'

export default {
  components: { SingleMovie },
  props: {
    movies: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <h5>Movie list</h5>
  <ul>
    <SingleMovie v-for="movie in movies" :movie="movie" />
  </ul>
</template>

<style scoped>

</style>