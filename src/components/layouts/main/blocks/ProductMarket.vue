<template>
  <div class="button-section">
    <div v-for="(button, i) in buttons" :key="i">
      <circular-button :icon="button.icon" :label="button.title" />
    </div>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";
import CircularButton from "@/components/CircularButton.vue";
import { buttons } from "@/assets/data/productMarketButtons";

@Options({
  components: {
    CircularButton,
  },
  data() {
    return {
      buttons,
    };
  },
  methods: {
    getButtons: function () {
      this.buttons = buttons;
    },
  },
  mounted: function () {
    this.getButtons();
  },
})
export default class ProductMarketButtons extends Vue {}
</script>

<style lang="scss" scoped>
.button-section {
  display: none;

  @media screen and (max-width: 600px) {
    display: flex;
    justify-content: space-evenly;
    margin: 1rem;
  }
}
</style>
