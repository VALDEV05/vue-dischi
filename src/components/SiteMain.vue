<template>
  <main id="siteMain"></main>
</template>

<script>
import axios from "axios";
export default {
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        console.log(r.data);
      })
      .catch((e) => {
        console.log(e, "OPS!!");
      });
  },
};
</script>

<style lang="scss">
@import "../assets/scss/color.scss";
#siteMain {
  height: 700px;
  width: 100vw;
  background-color: $background-color-main;
}
</style>