<template>
  <div class="container">
    <div class="img-container">
      <img :src="icon" />
    </div>
    <span>{{ label }}</span>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({
  props: ["label", "icon"],
})
export default class CircularButton extends Vue {}
</script>

<style lang="scss" scoped>
.img-container {
  border-radius: 100%;
  width: 80px;
  height: 80px;
  display: flex;
  align-items: center;
  background-color: var(--white);

  img {
    width: 2rem;
    margin: auto;
  }
}

span {
  font-size: 1rem;
  margin: 0.5rem;
}
</style>
