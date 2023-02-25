<template>
  <div class="MovieAddForm py-4">
    <div class="container">
      <div class="row">
        <div class="col-10 mx-auto">
          <h5>Create a movie</h5>
          <form @submit.prevent class="d-flex align-items-center">
            <input
              :value="name"
              @input="name = $event.target.value"
              required
              placeholder="Name of movie"
              type="text"
              class="form-control"
            />
            <input
              :value="viewers"
              @input="viewers = $event.target.value"
              required
              placeholder="How many times have seen"
              type="number"
              class="form-control"
            />
            <button @click="addMovie" class="btn btn-outline-dark">Create</button>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: '',
      viewers: ''
    }
  },
  methods: {
    addMovie() {
      const newMovie = {
        name: this.name,
        viewers: this.viewers,
        favorite: false,
        like: false,
        id: Date.now()
      }
      this.$emit('createMovie', newMovie)
      this.name = ''
      this.viewers = ''
    }
  }
}
</script>
<style></style>
