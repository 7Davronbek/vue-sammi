<script>
import AppInfo from '../app-info/AppInfo.vue'
import SearchPanel from '../search-panel/SearchPanel.vue'
import AppFilter from '../app-filter/AppFilter.vue'
import MovieList from '../movie-list/MovieList.vue'
import MovieAddForm from '../movie-add-form/MovieAddForm.vue'
export default {
  components: {
    AppInfo,
    SearchPanel,
    AppFilter,
    MovieList,
    MovieAddForm
  },
  data() {
    return {
      movies: [
        {
          name: 'Omar',
          viewers: 204,
          like: true,
          favorite: true
        },
        {
          name: 'Golder',
          viewers: 463,
          like: false,
          favorite: false
        },
        {
          name: "Truman's show",
          viewers: 998,
          like: false,
          favorite: true
        }
      ]
    }
  }
}
</script>

<template>
  <div>
    <div class="shadow">
      <AppInfo
        :allMoviesCount="movies.length"
        :favorite="movies.filter((i) => i.favorite).length"
      />
    </div>
    <div class="shadow">
      <SearchPanel />
      <AppFilter />
    </div>
    <div class="shadow">
      <MovieList :movies="movies" />
    </div>
    <div class="shadow">
      <MovieAddForm />
    </div>
  </div>
</template>

<style></style>
