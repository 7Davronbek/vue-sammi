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
          id: 1,
          name: 'Omar',
          viewers: 204,
          like: true,
          favorite: true
        },
        {
          id: 2,
          name: 'Golder',
          viewers: 463,
          like: false,
          favorite: false
        },
        {
          id: 3,
          name: "Truman's show",
          viewers: 998,
          like: false,
          favorite: true
        }
      ]
    }
  },

  methods: {
    createMovie(item) {
      this.movies.push(item)
    },
    onToogleHandler({ id, prop }) {
      this.movies = this.movies.map((item) => {
        if (item.id == id) {
          return { ...item, [prop]: !item[prop] }
        }
        return item
      })
    },
    onRemoveHandler(id) {
      this.movies = this.movies.filter((item) => item.id !== id)
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
        :like="movies.filter((i) => i.like).length"
      />
    </div>
    <div class="shadow">
      <SearchPanel />
      <AppFilter />
    </div>
    <div class="shadow">
      <MovieList :movies="movies" @onToogle="onToogleHandler" @onRemove="onRemoveHandler" />
    </div>
    <div class="shadow">
      <MovieAddForm @createMovie="createMovie" />
    </div>
  </div>
</template>

<style></style>
