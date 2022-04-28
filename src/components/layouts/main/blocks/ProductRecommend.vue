<template>
  <div class="recommend-section mx-05">
    <today-deal class="today-deal-section" />
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
import TodayDeal from "@/components/TodayDeal.vue";

@Options({
  components: {
    TodayDeal,
  },
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

  .today-deal-section {
    display: block;

    @media (max-width: 600px) {
      display: none;
    }
  }

  .recent-products {
    padding: 0rem;
    margin-left: 1rem;
    flex: 1;

    @media screen and (max-width: 600px) {
      padding: 0rem 0rem 1rem 0rem;
      margin-left: 0rem;
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
