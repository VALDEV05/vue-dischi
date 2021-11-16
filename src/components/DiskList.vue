<template>
  <div class="cards_disk">
    <SelectGenre :selectValue="searchValue" @filter_disk="searchDisk" />
    <div class="row gx-5 my-5 d-flex justify-content-center" v-if="!loading">
      <div
        class="col-md-2 text-center card_disk my-3"
        v-for="disk in filterDisks"
        :key="disk.title"
      >
        <div class="card rounded-0 p-4">
          <img :src="disk.poster" :alt="disk.author" class="img-fluid" />
          <h1 class="title mt-3">{{ disk.title }}</h1>
          <div class="text mt-4">
            <p>{{ disk.author }}</p>
            <p>{{ disk.year }}</p>
          </div>
        </div>
      </div>
    </div>
    <div v-else>
      <h2 class="loading text-light">Loading...</h2>
    </div>
  </div>
</template>

<script>
import axios from "axios";
import SelectGenre from "./SelectGenre.vue";

export default {
  components: {
    SelectGenre,
  },
  data() {
    return {
      disks: [],
      API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
      loading: true,
      searchValue: "",
    };
  },
  mounted() {
    setTimeout(this.callApi, 1500);
  },
  methods: {
    callApi() {
      axios
        .get(this.API_URL)
        .then((r) => {
          this.disks = r.data.response;
          this.loading = false;
        })
        .catch((e) => {
          console.log(e, "ERROR!");
        });
    },
    searchDisk(value) {
      this.searchValue = value;
    },
  },
  computed: {
    filterDisks() {
      if (this.searchValue === "All") {
        return this.disks;
      }
      const filterDisk = this.disks.filter((disk) =>
        disk.genre.includes(this.searchValue)
      );
      return filterDisk;
    },
  },
};
</script>

<style lang="scss">
@import "../assets/scss/color.scss";
.row {
  margin: 0 !important;

  .card {
    background-color: $background-color-card;
    height: 350px;
    .title {
      color: $color-title;
      text-transform: uppercase;
      font-size: 20px;
    }
    .text {
      color: $color-subtitle;
      font-size: 15px;
      p {
        margin-bottom: 0 !important;
      }
    }
  }
}
</style>