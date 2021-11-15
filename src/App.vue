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
