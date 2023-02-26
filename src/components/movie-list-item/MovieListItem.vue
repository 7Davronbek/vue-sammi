<template>
  <div class="d-flex align-items-center justify-content-between mb-3 border-bottom pb-3">
    <h6
      style="cursor: pointer"
      @click="$emit('onToogle', { id: movie.id, prop: 'like' })"
      :class="[{ favorite: movie.favorite }]"
    >
      {{ movie.name }}
    </h6>
    <input
      type="number"
      :class="[{ favorite: movie.favorite }]"
      :value="movie.viewers"
      class="form-control w-25 mx-4"
    />
    <div class="icon">
      <i @click="$emit('onToogle', { id: movie.id, prop: 'favorite' })" class="fa fa-cookie"></i>
      <i class="fa fa-trash mx-2"></i>
      <i class="fa fa-star" :class="[{ favorite: movie.like }]"></i>
    </div>
  </div>
</template>
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
<style>
.fa {
  cursor: pointer;
}
.fa-trash {
  color: rgb(255, 33, 33);
}
.fa-cookie {
  color: rgb(203, 75, 28);
}
.fa-star {
  color: #fff700;
  opacity: 0;
  visibility: hidden;
  transition: all 0.3s ease-in-out;
}

.fa-star.favorite {
  opacity: 1;
  visibility: visible;
}

h6.favorite,
input.favorite {
  color: #fff700;
  border-color: #fff700;
}
</style>
