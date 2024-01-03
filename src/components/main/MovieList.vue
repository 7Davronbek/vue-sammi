<script>

import SingleMovie from '@/components/main/SingleMovie.vue'

export default {
  components: { SingleMovie },
  props: {
    movies: {
      type: Array,
      required: true
    }
  },
  methods: {
    onLiked(item) {
      this.$emit('onLiked', item)
    }
  },
  emits: ['onLiked']
}
</script>

<template>
  <h5>Movie list</h5>
  <ul>
    <SingleMovie @onLiked="onLiked" :key="movie.id" v-for="movie in movies" :movie="movie" />
  </ul>
</template>

<style scoped>

</style>