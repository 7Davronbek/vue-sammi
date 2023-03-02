<template>
  <div class="SearchPanel py-4">
    <div class="container">
      <div class="row">
        <div class="col-lg-10 mx-auto">
          <input
            @input="changeHandler"
            :value="term"
            class="form-control"
            placeholder="Look for movie..."
            type="text"
          />
        </div>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    updateTermHandler: {
      type: Function,
      required: true
    }
  },
  data() {
    return {
      term: ''
    }
  },
  methods: {
    changeHandler(e) {
      this.term = e.target.value
      this.updateTermHandler(this.term)
    }
  }
}
</script>
<style scoped></style>
