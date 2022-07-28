.
<template>
  <main class="p-4">
    <MainHeader @selection="this.setValue" />
    <div class="container">
      <div class="row gy-4 my-5">
        <div
          v-for="album in filteredAlbums"
          :key="album.title"
          class="col my-2"
        >
          <BaseCard
            :artist="album.author"
            :img="album.poster"
            :title="album.title"
            :year="album.year"
            :genre="album.genre"
            :isLoading="isLoading"
            :albums="albums"
          />
        </div>
      </div>
    </div>
  </main>
</template>

<script>
import BaseCard from "./BaseCard.vue";
import MainHeader from "./MainHeader.vue";
export default {
  name: "TheMain",

  data() {
    return {
      selected: "",
      //filteredAlbums: [],
    };
  },

  components: {
    BaseCard,
    MainHeader,
  },
  props: {
    albums: Array,
    isLoading: Boolean,
  },
  methods: {
    setValue(select) {
      this.selected = select;
      console.log(select);
      console.log(this.filteredAlbums);
    },
  },
  computed: {
    filteredAlbums() {
      if (!this.selected) return this.albums;
      return this.albums.filter((album) => {
        return album.genre.toLowerCase() === this.selected;
      });
    },
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
