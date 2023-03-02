<template>
  <div class="AppFilter pb-4">
    <div class="container">
      <div class="row">
        <div class="col-lg-10 mx-auto">
          <div class="d-flex align-items-center">
            <button
              :class="[filterName === 'all' ? 'btn-dark' : 'btn-outline-dark']"
              @click="fitlerHandler('all')"
              class="btn me-2"
            >
              All
            </button>
            <button
              :class="[filterName === 'popular' ? 'btn-dark' : 'btn-outline-dark']"
              @click="fitlerHandler('popular')"
              class="btn me-2"
            >
              Popular
            </button>
            <button
              :class="[filterName === 'mostViewers' ? 'btn-dark' : 'btn-outline-dark']"
              @click="fitlerHandler('mostViewers')"
              class="btn me-2"
            >
              Most Viewed
            </button>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    updateFilterHandler: {
      type: Function,
      required: true
    },
    filterName: {
      type: String,
      required: true
    }
  },
  data() {
    return {
      filter: 'all'
    }
  },
  methods: {
    fitlerHandler(fitler) {
      this.fitler = fitler
      this.updateFilterHandler(this.fitler)
    }
  }
}
</script>
<style scoped></style>
