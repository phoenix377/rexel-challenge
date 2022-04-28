<template>
  <div class="shadow today-deals">
    <img src="@/assets/img/panel/deal.png" />
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class TodayDeal extends Vue {}
</script>

<style lang="scss" scoped>
.today-deals {
  flex: 1;

  img {
    width: 100%;
    height: 100%;
  }
}
</style>
