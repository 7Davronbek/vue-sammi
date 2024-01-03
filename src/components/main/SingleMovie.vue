<script>
export default {
  props: {
    movie: {
      type: Object,
      required: true
    }
  },
  methods: {
    onLiked(id) {
      this.$emit('onLiked', id)
    }
  },
  emits: ['onLiked', "onFavourite", "remove"]
}
</script>

<template>

  <li class="d-flex align-items-center justify-content-between border-bottom py-4"
      :class="[{favorite: movie.favorite}, {liked: movie.liked}]"
  >
    <span @click="onLiked(movie.id)">{{ movie.name }}</span>
    <div class="d-flex align-items-center">
      <h6 class="mb-0 mx-3">{{ movie.viewers }}</h6>
      <button @click="$emit('onFavourite', movie.id)" class="btn mx-2">Cookie</button>
      <button @click="$emit('remove', movie.id)" class="btn mx-2 btn-danger">Trash</button>
      <button class="btn mx-2 btn-warning">Star</button>
    </div>
  </li>
</template>

<style lang="scss">
li {
  .btn-warning {
    display: none;
  }

  &.favorite {
    background-color: #ccc;
  }

  &.liked {
    .btn-warning {
      display: block;
    }
  }
}
</style>