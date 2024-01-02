<script>

import Info from '@/components/main/Info.vue'
import SearchPanel from '@/components/main/SearchPanel.vue'
import AppFilter from '@/components/main/AppFilter.vue'
import MovieList from '@/components/main/MovieList.vue'
import MovieAddForm from '@/components/main/MovieAddForm.vue'

export default {
  components: { MovieAddForm, MovieList, AppFilter, SearchPanel, Info },

  props: {
    movies: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <div class="container pb-5">
    <div class="row">
      <div class="col-12">
        <div class="mb-5"></div>
        <Info :favoriteCount="movies.filter(m => m.favorite).length" :moviesCount="movies.length" />
        <div class="mb-5"></div>
        <SearchPanel />
        <div class="mb-5"></div>
        <AppFilter />
        <div class="mb-5"></div>
        <MovieList :movies="movies" />
        <div class="mb-5"></div>
        <MovieAddForm />
      </div>
    </div>
  </div>
</template>

<style scoped>

</style>