.
<template>
  <header>
    <img class="img-fluid" src="../assets/logo.svg" alt="logo" id="logo" />
    <BaseSelect
      :options="options"
      :select-title="selectTitle"
      @selection="this.sendValue"
    />
  </header>
</template>

<script>
import BaseSelect from "./BaseSelect.vue";
export default {
  name: "MainHeader",
  components: { BaseSelect },
  data() {
    return {
      selectTitle: "Seleziona un genere",
      selectValue: this.select,
      options: [
        { option: "Rock", value: "rock" },
        { option: "Metal", value: "metal" },
        { option: "Jazz", value: "jazz" },
        { option: "Pop", value: "pop" },
      ],
    };
  },
  methods: {
    sendValue(select) {
      this.$emit("selection", select);
    },
  },

  props: {
    albums: Array,
  },
};
</script>

<style lang="scss">
header {
  background-color: #2e3a46;
  height: 70px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
  #logo {
    width: 40px;
  }
}
</style>
