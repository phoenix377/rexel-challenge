<template>
  <div class="shadow bg-white banner-section">
    <a class="banner-img" href="#"></a>
    <a href="#">Shop better, download the Platt App today</a>
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class AppBanner extends Vue {}
</script>

<style lang="scss" scoped>
.banner-section {
  margin: 1rem 0.5rem;
  padding-bottom: 1rem;
  text-align: center;

  a {
    display: block;
    text-decoration: none;
    font-weight: bold;
    color: black;

    &.banner-img {
      height: 200px;
      margin-bottom: 1rem;
      background-image: url("@/assets/img/panel/app-get-banner.png");
      background-position: right;
      background-size: cover;
    }

    p {
      font-size: 0.8rem;
      font-weight: bold;
    }
  }
}
</style>
