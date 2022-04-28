<template>
  <app-main />
</template>

<script>
import { Options, Vue } from "vue-class-component";
import AppMain from "@/layouts/AppMain.vue";

@Options({
  components: {
    AppMain,
  },
})
export default class App extends Vue {}
</script>
<style>
:root {
  --green: #008833;
  --white: #ffffff;
  --grey: rgb(88, 88, 88);
  --grey-light: #ccc;
  --background-grey: #eee;
  --shadow-grey: #999;
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
</style>
