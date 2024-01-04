<script>

import HomeView from '@/views/HomeView.vue'
import axios from 'axios'

export default {
  components: { HomeView },

  data() {
    return {
      movies: [],
      term: 'aut'
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

    onSearchFilter(arr, term) {
      if (term.length === 0) {
        return arr
      }
      return arr.filter(m => m.name.toLowerCase().indexOf(term) > -1)
    },

    onUpdateTermHandler(term) {
      this.term = term
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
  <HomeView :onUpdateTermHandler="onUpdateTermHandler"  @remove="remove" @onFavourite="onFavourite" @onLiked="onLiked" @newMovie="newMovie"
            :movies="onSearchFilter(movies, term)" />
</template>

<style>

@import "@/style/main.scss";
</style>