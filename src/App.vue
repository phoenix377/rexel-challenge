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
