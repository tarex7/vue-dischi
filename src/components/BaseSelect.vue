.
<template>
  <select v-model="select" @change="emit" class="form-select">
    <option selected>{{ selectTitle }}</option>
    <option v-for="option in options" :key="option.value" :value="option.value">
      {{ option.option }}
    </option>
  </select>
</template>

<script>
export default {
  name: "BaseSelect",
  data() {
    return {
      select: this.selectTitle,
    };
  },
  props: {
    options: Array,
    selectTitle: String,
  },
  methods: {
    emit() {
      this.$emit("selection", this.select);
    },
  },
};
</script>

<style lang="scss" scoped>
.form-select {
  width: 10%;
  height: 70%;
}
</style>
