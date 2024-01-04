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
    <FormControl required v-model="name"  placeholder="Movie name" />
    <FormControl required v-model="viewers" type="number" placeholder="Viewed" />
    <PrimaryButton type="submit" class="btn-outline-dark">Add</PrimaryButton>
  </form>
</template>

<style scoped>

</style>