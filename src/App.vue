<script>

import HomeView from '@/views/HomeView.vue'

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
        },
        {
          id: 2,
          name: 'Ipsum',
          viewers: 312,
          favorite: false,
          liked: false
        },
        {
          id: 3,
          name: 'Dolor',
          viewers: 746,
          favorite: false,
          liked: true
        },
        {
          id: 4,
          name: 'Morel',
          viewers: 1591,
          favorite: true,
          liked: true
        },
        {
          id: 5,
          name: 'Lodor',
          viewers: 12,
          favorite: true,
          liked: false
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
    }
  }
}
</script>

<template>
  <HomeView @remove="remove" @onFavourite="onFavourite" @onLiked="onLiked" @newMovie="newMovie" :movies="movies" />
</template>

<style>

@import "@/style/main.scss";
</style>