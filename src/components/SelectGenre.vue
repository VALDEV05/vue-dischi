<template>
  <select id="select" class="form-select me-5">
    <option selected>Select genre</option>
    <option value="all">All</option>
    <option value="pop">Pop</option>
    <option value="rock">Rock</option>
    <option value="jazz">Jazz</option>
    <option value="metal">Metal</option>
  </select>
</template>

<script>
export default {};
</script>

<style lang="scss">
#select {
  background-color: $brand-color-main !important;
  width: 200px;
}
</style>