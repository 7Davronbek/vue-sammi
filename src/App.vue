<script>

import HomeView from '@/views/HomeView.vue'
import axios from 'axios'

export default {
  components: { HomeView },

  data() {
    return {
      movies: [
        {
          id: 1,
          name: 'Lorem',
          viewers: 123,
          favorite: true,
          liked: true
        }
      ]
    }
  },
  methods: {
    newMovie(item) {
      this.movies.push(item)
    },
    onLiked(id) {
      this.movies.map(i => {
        if (i.id === id) {
          i.liked = !i.liked
        }
        return i
      })
    },
    onFavourite(id) {
      this.movies.map(item => {
        if (item.id === id) {
          item.favorite = !item.favorite
        }
        return item
      })
    },
    remove(id) {
      this.movies = this.movies.filter(item => item.id !== id)
    },
    async fetchMovie() {
      const { data } = await axios.get('https://jsonplaceholder.typicode.com/posts?_limit=10')
      this.movies = data.map((item) => ({
        id: item.id,
        name: item.title,
        viewers: item.id * 69,
        favorite: false,
        liked: false
      }))
    }
  },
  mounted() {
    this.fetchMovie()
  }
}
</script>

<template>
  <HomeView @remove="remove" @onFavourite="onFavourite" @onLiked="onLiked" @newMovie="newMovie" :movies="movies" />
</template>

<style>

@import "@/style/main.scss";
</style>