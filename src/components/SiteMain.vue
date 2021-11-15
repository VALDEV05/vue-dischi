<template>
  <main id="siteMain">
    <div class="row d-flex justify-content-center">
      <div class="col-lg-2 col-md-4 col-sm-6 col-xs-12 mt-5">
        <div class="card border-0">
          <div class="card-body d-flex flex-column align-items-center">
            <img
              src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg"
              alt=""
            />
            <h3 class="card-title">Title</h3>
            <p class="card-subtitle">Text</p>
          </div>
        </div>
      </div>
    </div>
  </main>
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
  .card {
    height: 400px;
    background-color: $background-color-card;
    .card-body {
      img {
        height: 150px;
      }
      .card-title {
        color: $color-title;
      }
      .card-subtitle {
        color: $color-subtitle;
      }
    }
  }
}
</style>