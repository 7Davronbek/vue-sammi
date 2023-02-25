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
  }
}
</script>

<template>
  <div>
    <AppInfo />
    <SearchPanel />
    <AppFilter />
    <MovieList />
    <MovieAddForm />
  </div>
</template>

<style></style>
