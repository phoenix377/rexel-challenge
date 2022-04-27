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
:root {
  --green: #008833;
  --white: #ffffff;
  --grey: rgb(88, 88, 88);
  --grey-light: #ccc;
  --background-grey: #eee;
}
body {
  background-color: var(--background-grey);
  margin: 0px;
}
.container {
  display: flex;
  align-items: center;
  flex-direction: column;
  margin: 0px;
}
.w-full {
  width: 100%;
}
.shadow {
  box-shadow: 0 0 5px 1px #999;
}
.bg-white {
  background-color: var(--white);
}
</style>
