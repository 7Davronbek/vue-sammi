<template>
  <div>
    <div class="container">
      <div class="row">
        <div class="col-12">
          <h1>Hello world!</h1>
          <button @click="decrement" class="btn btn-danger me-3">-</button>
          {{ counter }}
          <button @click="increment" class="btn btn-success ms-3">+</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      counter: 0
    }
  },
  methods: {
    increment() {
      this.counter += 1
    },
    decrement() {
      this.counter -= 1
    }
  }
}
</script>

<style></style>
