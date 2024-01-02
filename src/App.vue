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
  }

}
</script>

<template>
  <HomeView :movies="movies" />
</template>

<style>

@import "@/style/main.scss";
</style>