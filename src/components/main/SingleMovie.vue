<script>
export default {
  props: {
    movie: {
      type: Object,
      required: true
    }
  }
}
</script>

<template>

  <li class="d-flex align-items-center justify-content-between border-bottom py-4"
      :class="[{favorite: movie.favorite}, {liked: movie.liked}]"
  >
    <span>{{ movie.name }}</span>
    <div class="d-flex align-items-center">
      <h6 class="mb-0 mx-3">{{ movie.viewers }}</h6>
      <button class="btn mx-2">Cookie</button>
      <button class="btn mx-2 btn-danger">Trash</button>
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