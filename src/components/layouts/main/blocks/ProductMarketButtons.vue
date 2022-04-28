<template>
  <div class="markets-section">
    <div class="button-section">
      <div v-for="(button, i) in buttons" :key="i">
        <circular-button :icon="button.icon" :label="button.title" />
      </div>
    </div>
    <div class="product-market-section mx-05">
      <h3>Product Markets</h3>
      <div class="market-container">
        <market-item
          v-for="(product, i) of productMarkets"
          :key="i"
          :image="product.image"
          :label="product.label"
        />
      </div>
    </div>
    <today-deal class="today-deal-section" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import CircularButton from "@/components/CircularButton.vue";
import MarketItem from "@/components/MarketItem.vue";
import TodayDeal from "@/components/TodayDeal.vue";
import { buttons } from "@/assets/data/productMarketButtons";
import { productMarkets } from "@/assets/data/productMarkets";

@Options({
  components: {
    CircularButton,
    MarketItem,
    TodayDeal,
  },
  data() {
    return {
      buttons,
      productMarkets,
    };
  },
})
export default class ProductMarketButtons extends Vue {}
</script>

<style lang="scss" scoped>
.markets-section {
  margin: 0rem 0rem 1rem 0rem;

  .button-section {
    display: none;

    @media screen and (max-width: 600px) {
      display: flex;
      justify-content: space-around;
      margin: 1rem 0.5rem;
    }
  }

  .product-market-section {
    .market-container {
      display: flex;
    }
    h3 {
      text-align: center;
      font-size: 1.5rem;
    }
    @media screen and (max-width: 600px) {
      display: none;
    }
  }

  .today-deal-section {
    display: none;

    @media (max-width: 600px) {
      display: flex;
      margin: 0.5rem;
    }
  }
}
</style>
