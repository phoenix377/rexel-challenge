<template>
  <category-block />
  <product-market-buttons />
  <pay-wall />
  <product-recommend />
  <page-recommend />
  <app-banner />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import CategoryBlock from "@/components/layouts/main/blocks/CategoryBlock.vue";
import ProductMarketButtons from "@/components/layouts/main/blocks/ProductMarket.vue";
import PayWall from "@/components/layouts/main/blocks/PayWall.vue";
import ProductRecommend from "@/components/layouts/main/blocks/ProductRecommend.vue";
import PageRecommend from "@/components/layouts/main/blocks/PageRecommend.vue";
import AppBanner from "@/components/layouts/main/blocks/AppBanner.vue";

@Options({
  components: {
    CategoryBlock,
    ProductMarketButtons,
    PayWall,
    ProductRecommend,
    PageRecommend,
    AppBanner,
  },
})
export default class HomeView extends Vue {}
</script>
