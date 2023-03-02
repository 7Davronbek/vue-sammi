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
      ],
      term: '',
      filter: 'all'
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
    },
    onSearchHandler(arr, term) {
      if (term.length === 0) {
        return arr
      }

      return arr.filter((item) => item.name.toLowerCase().indexOf(term) > -1)
    },

    updateTermHandler(term) {
      this.term = term
    },
    onFilterHandler(arr, filter) {
      switch (filter) {
        case 'popular':
          return arr.filter((item) => item.like)

        case 'mostViewers':
          return arr.filter((item) => item.viewers > 500)

        default:
          return arr
      }
    },
    updateFilterHandler(filter) {
      this.filter = filter
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
      <SearchPanel :updateTermHandler="updateTermHandler" />
      <AppFilter :updateFilterHandler="updateFilterHandler" :filterName="filter" />
    </div>
    <div class="shadow">
      <MovieList
        :movies="onFilterHandler(onSearchHandler(movies, term), filter)"
        @onToogle="onToogleHandler"
        @onRemove="onRemoveHandler"
      />
    </div>
    <div class="shadow">
      <MovieAddForm @createMovie="createMovie" />
    </div>
  </div>
</template>

<style></style>
