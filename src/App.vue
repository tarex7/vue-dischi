<template>
  <div>
    <MainHeader />
    <TheMain :albums="albums" :isLoading="isLoading" />
  </div>
</template>

<script>
import MainHeader from "./components/MainHeader.vue";
import TheMain from "./components/TheMain.vue";
import axios from "axios";
export default {
  name: "App",
  data() {
    return {
      albums: [],
      isLoading: true,
      URI: "https://flynn.boolean.careers/exercises/api/array",
    };
  },
  components: {
    MainHeader,
    TheMain,
  },
  methods: {
    getData() {
      axios.get(`${this.URI}/music`).then((res) => {
        this.albums = res.data.response;
        const loadingDelay = () => {
          this.isLoading = false;
        };
        setTimeout(loadingDelay, 3000);
      });
    },
  },
  mounted() {
    this.getData();
  },
};
</script>

<style lang="scss">
@import "~bootstrap/scss/bootstrap";
@import "./assets/style.scss";
</style>
