<template>
  <div class="container">
    <div class="left-item">
      <img :src="leftIcon" />
      <span class="label">{{ label }}</span>
    </div>
    <img class="right-item" :src="rightIcon" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: ["label", "leftIcon", "rightIcon", "type"],
})
export default class CategoryItem extends Vue {}
</script>

<style lang="scss" scoped>
.container {
  padding: 1rem;
  flex-direction: row;
  justify-content: space-between;

  .left-item {
    display: flex;
    align-items: center;

    @media (min-width: 600px) {
      margin: auto;
    }

    img {
      height: 20px;

      @media (max-width: 600px) {
        width: 20px;
      }
    }

    span {
      margin-left: 1rem;
    }
  }

  .right-item {
    width: 1rem;
    @media (min-width: 600px) {
      display: none;
    }
  }
}
</style>
