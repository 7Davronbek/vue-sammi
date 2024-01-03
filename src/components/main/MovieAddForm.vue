<script>
export default {
  data() {
    return {
      name: '',
      viewers: ''
    }
  },
  methods: {
    changeHandlerName(e) {
      console.log(e.target.value)
    },
    addMovie(e) {
      e.preventDefault()
      const newMovie = {
        id: Math.random(),
        name: this.name,
        viewers: this.viewers,
        favorite: false,
        liked: false
      }
      this.$emit('newMovie', newMovie)
      this.name = ''
      this.viewers = ''
    }
  },
  emits: ['newMovie']
}
</script>

<template>
  <h4>Add movie</h4>
  <form @submit="addMovie">
    <input @input="name = $event.target.value" :value="name" type="text" placeholder="Movie name"
           class="form-control mb-3">
    <input @input="viewers = $event.target.value" :value="viewers" type="text" placeholder="Viewed"
           class="form-control mb-3">
    <button type="submit" class="btn btn-outline-dark">Add</button>
  </form>
</template>

<style scoped>

</style>