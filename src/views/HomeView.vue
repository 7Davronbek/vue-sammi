<script>
import MainVue from '@/components/main/MainVue.vue'

export default {
  components: { MainVue },
  props: {
    movies: {
      type: Array,
      required: true
    }
  },
  methods: {
    newMovie(newMovie) {
      this.$emit('newMovie', newMovie)
    },
    onLiked(item) {
      this.$emit('onLiked', item)
    }
  },
  emits: ["newMovie", "onLiked"]
}
</script>

<template>
  <MainVue @newMovie="newMovie" @onLiked="onLiked" :movies="movies" />
</template>
