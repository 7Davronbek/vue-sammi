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
    },
    onFavourite(item) {
      this.$emit("onFavourite", item)
    },
    remove(item) {
      this.$emit('remove', item)
    }
  },
  emits: ['newMovie', 'onLiked', 'onFavourite', "remove"]
}
</script>

<template>
  <MainVue @remove="remove" @onFavourite="onFavourite" @newMovie="newMovie" @onLiked="onLiked" :movies="movies" />
</template>
