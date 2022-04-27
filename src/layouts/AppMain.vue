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
import AppHeader from "@/components/layouts/main/AppHeader.vue";
import AppFooter from "@/components/layouts/main/AppFooter.vue";

export default {
  name: "AppMain",
  components: {
    AppHeader,
    AppFooter,
  },
};
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
</style>
