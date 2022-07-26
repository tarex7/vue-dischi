.
<template>
  <header>
    <img class="img-fluid" src="../assets/logo.svg" alt="logo" id="logo" />
  </header>
</template>

<script>
export default {
  name: "MainHeader",
};
</script>

<style lang="scss">
header {
  background-color: #2e3a46;
  height: 70px;
  display: flex;
  padding: 0 20px;
  #logo {
    width: 40px;
  }
}
</style>
