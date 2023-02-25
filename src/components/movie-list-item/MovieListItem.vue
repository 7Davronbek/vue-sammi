<template>
  <div class="d-flex align-items-center justify-content-between mb-3 border-bottom pb-3">
    <h6>Omar Ibn Hattob</h6>
    <input type="number" defaultValue="999" class="form-control w-25 mx-4" />
    <div class="icon">
      <i class="fa fa-cookie "></i>
      <i class="fa fa-trash mx-2"></i>
      <i class="fa fa-star"></i>
    </div>
  </div>
</template>
<script>
export default {}
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
}

h6.favorite {
    color: #fff700;
}

</style>
