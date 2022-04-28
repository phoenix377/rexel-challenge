<template>
  <div class="recommend-section mx-05">
    <div class="shadow today-deals">
      <img src="@/assets/img/panel/deal.png" />
    </div>
    <div class="shadow bg-white recent-products">
      <div class="header">
        <span>Recently Viewed</span>
        <a href="#" class="link">View all</a>
      </div>
      <div class="images">
        <img
          v-for="(productImg, i) in recentProducts"
          :key="i"
          :src="productImg"
        />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import { recentProducts } from "@/assets/data/recentProducts";

@Options({
  data() {
    return { recentProducts };
  },
})
export default class ProductRecommend extends Vue {}
</script>

<style lang="scss" scoped>
.recommend-section {
  display: flex;
  flex-direction: row;
  margin: 1rem 0.5rem;

  .today-deals {
    flex: 1;

    @media screen and (max-width: 600px) {
      display: none;
    }

    img {
      width: 100%;
      height: 100%;
    }
  }

  .recent-products {
    padding: 0rem;
    flex: 1;

    @media screen and (max-width: 600px) {
      padding: 1rem 0rem;
    }

    .header {
      display: flex;
      justify-content: space-between;
      font-weight: bold;
      padding: 1rem;

      a {
        color: var(--green);
      }
    }

    .images {
      display: flex;
      justify-content: space-evenly;

      img {
        max-width: 33%;
      }
    }
  }
}
</style>
