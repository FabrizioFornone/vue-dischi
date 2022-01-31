<template>
  <header>
    <div class="mx-3 py-2 d-flex justify-content-between">
      <img class="" src="@/assets/logo-small.svg" alt="" />
      <loader v-if="discsList.length < 10" />
    </div>
  </header>
</template>

<script>
import Loader from "./Loader.vue";
export default {
  components: { Loader },
  props: {
    discsList: Array,
  },
};
</script>

<style lang="scss" scoped LoaderComponent>
@import "@/style/headerBox.scss";
</style>
