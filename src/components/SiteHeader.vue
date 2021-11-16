

<template>
  <header
    id="siteHeader"
    class="d-flex align-items-center justify-content-between"
  >
    <img
      id="logo_spotify"
      src="../assets/img/Spotify_logo_without_text.svg"
      class="ms-4"
      alt="Logo"
    />
    <Select />
  </header>
</template>

<script>
import Select from "./SelectGenre.vue";
export default {
  components: {
    Select,
  },
};
</script>

<style lang="scss">
@import "../assets/scss/color.scss";
#siteHeader {
  background-color: $background-color-header;
  height: 80px;
  width: 100vw;
  #logo_spotify {
    height: 50px;
  }
}
</style>