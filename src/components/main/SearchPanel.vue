<script>
export default {
  data() {
    return {
      term: ''
    }
  },
  methods: {
    changeHandler(e) {
      this.term = e.target.value
      this.onUpdateTermHandler(this.term)
    }
  },
  props: {
    onUpdateTermHandler: {
      type: Function,
      required: true
    }
  }
}
</script>

<template>
  <FormControl @input="changeHandler" v-model="term" placeholder="Find movie" />
</template>

<style scoped>

</style>