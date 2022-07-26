.
<template>
  <div class="card p-4 text-center text-white">
    <figure><img class="img-fluid" :src="img" alt="title" /></figure>
    <h3 class="title text-uppercase mb-3">{{ title }}</h3>
    <h5 class="artist m-0 text-muted">{{ artist }}</h5>
    <h5 class="year text-muted">{{ year }}</h5>
  </div>
</template>

<script>
export default {
  name: "BaseCard",
  props: {
    artist: String,
    title: String,
    img: String,
    year: String,
  },
};
</script>

<style lang="scss" scoped>
img {
  min-width: 185px;
  min-height: 185px;
}

.card {
  background-color: #2e3a46;
  cursor: pointer;
  border: 3px solid transparent;
  transition: all 0.2s;
  &:hover {
    border: 3px solid rgba($color: #fff, $alpha: 0.5);
  }
}
</style>
