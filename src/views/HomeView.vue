<script>
import MainVue from '@/components/main/MainVue.vue'

export default {
  components: { MainVue },
  props: {
    movies: {
      type: Array,
      required: true
    }
  }
}
</script>

<template>
  <MainVue :movies="movies" />
</template>
