<template>
  <div id="app">
    <header id="siteHeader" class="d-flex align-items-center">
      <img
        id="logo_spotify"
        src="./assets/img/Spotify_logo_without_text.svg"
        class="ms-4"
        alt="Logo"
      />
    </header>
    <!-- /#siteHeader -->
    <main id="siteMain"></main>
    <!-- /#siteMain -->
  </div>
</template>

<script>
/* import axios from "axios"; */
export default {
  name: "App",
  data() {
    return {
      characters: [],
    };
  },
  /* mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        console.log(r.data);
      })
      .catch((e) => {
        console.log(e, "OPS!!");
      });
  }, */
};
</script>


<style lang="scss">
@import "../node_modules/bootstrap/scss/bootstrap.scss";
@import "./assets/scss/color.scss";
#siteHeader {
  background-color: $background-color-header;
  height: 80px;
  width: 100vw;
  #logo_spotify {
    height: 50px;
  }
}
#siteMain {
  height: 700px;
  width: 100vw;
  background-color: $background-color-main;
}
</style>
