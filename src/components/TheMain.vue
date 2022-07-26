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
  },
};
</script>

<style lang="scss" scoped>
.row {
  background-color: #1e2d3b;
}

.card {
  height: 430px;
}
</style>
