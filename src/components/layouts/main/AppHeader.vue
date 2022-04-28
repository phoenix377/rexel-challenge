<template>
  <div class="container">
    <div class="header">
      <div class="logo">
        <img src="@/assets/logo.png" />
      </div>
      <div class="icons">
        <img src="@/assets/icon/white/ic_search.png" />
        <img src="@/assets/icon/white/ic_shopping_cart.png" />
        <img src="@/assets/icon/white/ic_person.png" />
        <img src="@/assets/icon/white/ic_menu.png" />
      </div>
    </div>
    <search-input placeholder="what are you looking for?" />
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import SearchInput from "@/components/SearchInput.vue";

@Options({
  components: {
    SearchInput,
  },
})
export default class AppHeader extends Vue {}
</script>

<style lang="scss" scoped>
.container {
  background-color: var(--green);
  padding: 0.5rem 1rem 1rem 0.5rem;
  justify-content: space-between;

  @media screen and (max-width: 600px) {
    padding: 1rem 0;
  }

  .header {
    width: 100%;
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    align-items: center;

    .logo {
      margin: 0.7rem;
    }

    .icons {
      flex-basis: 15%;
      display: flex;
      flex-direction: row;
      justify-content: space-around;
      align-items: center;

      @media screen and (max-width: 600px) {
        flex-basis: 40%;
        justify-content: space-evenly;
      }

      img {
        width: 1rem;
        height: 1rem;
      }
    }
  }
}
</style>
