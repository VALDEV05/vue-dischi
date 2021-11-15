<template>
  <main id="siteMain" class="px-3 py-5">
    <DiskList />
  </main>
</template>

<script>
import DiskList from "./DiskList.vue";
export default {
  components: {
    DiskList,
  },
};
</script>
<style lang="scss">
@import "../assets/scss/color.scss";
main {
  background-color: $background-color-main;
}
</style>