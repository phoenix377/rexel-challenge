<template>
  <category-block />
  <product-market-buttons />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import CategoryBlock from "@/components/layouts/main/blocks/CategoryBlock.vue";
import ProductMarketButtons from "@/components/layouts/main/blocks/ProductMarket.vue";

@Options({
  components: {
    CategoryBlock,
    ProductMarketButtons,
  },
})
export default class HomeView extends Vue {}
</script>
