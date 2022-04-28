<template>
  <div class="bg-white shadow paywall-section">
    <img src="@/assets/img/platt-plus.png" />
    <div>
      <h2>Get Started Today</h2>
      <h2 class="sub-title">
        <span>Become a </span>
        <span class="green">Platt Plus </span>
        <span>Member</span>
      </h2>
      <button>Learn More</button>
    </div>
  </div>
</template>

<script lang="ts">
import { Vue } from "vue-class-component";

export default class PayWall extends Vue {}
</script>

<style lang="scss" scoped>
.paywall-section {
  margin: 1rem 0.5rem;
  padding: 2rem 1rem;
  text-align: center;

  > div {
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin: 1rem 0rem;
  }

  h2 {
    margin: 0;
    &.sub-title {
      margin: 0;
      padding-bottom: 0.5rem;
    }

    span.green {
      color: var(--green);
    }
  }

  button {
    width: 50%;
    border-radius: 5rem;
    margin: 0.5rem auto;
    padding: 0.8rem;
    border: none;
  }

  @media screen and (min-width: 600px) {
    display: flex;

    > img,
    > div {
      flex-basis: 50%;
    }
  }
}
</style>
