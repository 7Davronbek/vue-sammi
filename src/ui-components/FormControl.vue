<script>
export default {
  name: 'FormControl',
  props: {
    modelValue: [String, Number]
  },
  methods: {
    updateInput(e) {
      this.$emit('update:modelValue', e.target.value)
    }
  }
}
</script>

<template>
  <input type="text"
         class="form-control mb-3"
         :value="modelValue"
         @input="updateInput"
  >
</template>

<style scoped>

</style>