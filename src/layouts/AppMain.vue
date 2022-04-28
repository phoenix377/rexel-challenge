<template>
  <div>
    <app-header />
    <main>
      <router-view />
    </main>
    <app-footer />
  </div>
</template>

<script>
import { Options, Vue } from "vue-class-component";
import AppHeader from "@/components/layouts/main/AppHeader.vue";
import AppFooter from "@/components/layouts/main/AppFooter.vue";

@Options({
  components: {
    AppHeader,
    AppFooter,
  },
})
export default class AppMain extends Vue {}
</script>

<style>
body {
  background-color: var(--background-grey);
  margin: 0px;
}
.shadow {
  box-shadow: 0 0 5px 1px var(--shadow-grey);
}
.bg-white {
  background-color: var(--white);
}
</style>
