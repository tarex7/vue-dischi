.
<template>
  <main class="p-4">
    <div class="container">
      <div class="row gy-4 my-5">
        <div v-for="album in albums" :key="album.title" class="col my-2">
          <BaseCard
            :artist="album.author"
            :img="album.poster"
            :title="album.title"
            :year="album.year"
            :isLoading="isLoading"
          />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import BaseCard from "./BaseCard.vue";
export default {
  name: "TheMain",

  components: {
    BaseCard,
  },
  props: {
    albums: Array,
    isLoading: Boolean,
  },
};
</script>

<style lang="scss" scoped>
.row {
  background-color: #1e2d3b;
}
.col {
  height: 430px;
  min-width: calc(100% / 5);
}
.card {
  height: 430px;
}
</style>
