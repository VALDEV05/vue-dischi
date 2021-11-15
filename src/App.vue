<template>
  <div id="app">
    <SiteHeader />
    <!-- /#siteHeader -->
    <SiteMain />

    <!-- /#siteMain -->
  </div>
</template>

<script>
import SiteHeader from "@/components/SiteHeader.vue";
import SiteMain from "@/components/SiteMain.vue";
/* import axios from "axios"; */
export default {
  name: "App",
  components: {
    SiteHeader,
    SiteMain,
  },
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

#siteMain {
  height: 700px;
  width: 100vw;
  background-color: $background-color-main;
}
</style>
