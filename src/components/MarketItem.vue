<template>
  <a :href="url ? url : '#'" class="market-card shadow bg-white">
    <img class="image" :class="fullWidth ? 'w-full' : ''" :src="image" />
    <span>{{ label }}</span>
  </a>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: ["image", "label", "fullWidth", "url"],
})
export default class MarketItem extends Vue {}
</script>

<style lang="scss" scoped>
.market-card {
  display: block;
  margin: 0 0.5rem;
  padding-bottom: 0.5rem;
  text-decoration: none;
  text-align: center;
  color: black;
  flex: 1;

  span {
    font-size: 0.8rem;
    font-weight: bold;
  }
}
</style>
