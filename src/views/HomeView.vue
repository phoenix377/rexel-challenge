<template>
  <category-block />
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import CategoryBlock from "@/components/layouts/main/blocks/CategoryBlock.vue";

@Options({
  components: {
    CategoryBlock,
  },
})
export default class HomeView extends Vue {}
</script>
