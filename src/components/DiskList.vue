<template>
  <div class="cards_disk">
    <div class="row gx-5 my-5 d-flex justify-content-center">
      <div
        class="col-md-2 text-center card_disk my-3"
        v-for="disk in disks"
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
  </div>
</template>

<script>
import axios from "axios";

export default {
  data() {
    return {
      disks: [],
      API_URL: "https://flynn.boolean.careers/exercises/api/array/music",
    };
  },
  mounted() {
    this.callApi();
  },
  methods: {
    callApi() {
      axios
        .get(this.API_URL)
        .then((r) => {
          this.disks = r.data.response;
        })
        .catch((e) => {
          console.log(e, "ERROR!");
        });
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