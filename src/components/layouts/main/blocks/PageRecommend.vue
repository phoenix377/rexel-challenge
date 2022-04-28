<template>
  <div class="page-section">
    <a
      v-for="(page, i) of recommendedPages"
      :key="i"
      :href="url ? url : '#'"
      class="shadow bg-white page-card"
    >
      <img :src="page.image" />
      <span>{{ page.label }}</span>
    </a>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import { recommendedPages } from "@/assets/data/recommendedPages";

@Options({
  data() {
    return { recommendedPages };
  },
})
export default class PageRecommend extends Vue {}
</script>

<style lang="scss" scoped>
.page-section {
  margin: 1rem 0rem;
  display: flex;
  flex-wrap: wrap;

  @media screen and (min-width: 600px) {
    align-items: stretch;
  }

  .page-card {
    display: flex;
    flex: 1;
    flex-direction: column;
    justify-content: space-between;
    align-items: center;
    margin: 0.5rem;
    padding: 0.5rem;
    text-decoration: none;
    text-align: center;
    color: black;

    @media screen and (max-width: 600px) {
      flex-basis: 40%;
    }

    span {
      font-weight: bold;
    }
  }
}
</style>
