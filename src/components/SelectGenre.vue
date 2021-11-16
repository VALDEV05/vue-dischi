<template>
  <select
    name="select"
    id="select"
    @change="$emit('filter_disk', selectValue)"
    v-model="selectValue"
    class="py-2 rounded-3"
  >
    <option value="All">Seleziona Genere (All)</option>
    <option v-for="genre in genres" :key="genre.author" :value="genre">
      {{ genre }}
    </option>
  </select>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      genres: [],
      selectValue: "All",
    };
  },
  mounted() {
    axios
      .get("https://flynn.boolean.careers/exercises/api/array/music")
      .then((r) => {
        r.data.response.forEach((album) => {
          if (!this.genres.includes(album.genre)) {
            this.genres.push(album.genre);
          }
        });
      });
  },
};
</script>

<style lang="scss">
@import "../assets/scss/color.scss";
#select {
  background-color: $brand-color-main !important;
  width: 200px;
  border: none;
}
</style> 