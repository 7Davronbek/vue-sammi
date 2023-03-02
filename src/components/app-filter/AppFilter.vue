<template>
  <div class="AppFilter pb-4">
    <div class="container">
      <div class="row">
        <div class="col-lg-10 mx-auto">
          <div class="d-flex align-items-center">
            <button
              v-for="btn in filterButtons"
              :key="btn.name"
              class="btn me-2"
              :class="[filterName === btn.name ? 'btn-dark' : 'btn-outline-dark']"
              @click="fitlerHandler(btn.name)"
            >
              {{ btn.title }}
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
      filter: 'all',
      filterButtons: [
        {
          name: 'all',
          title: 'All'
        },
        {
          name: 'popular',
          title: 'Popular'
        },
        {
          name: 'mostViewers',
          title: 'Most Viewed'
        }
      ]
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
