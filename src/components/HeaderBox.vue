<template>
  <header>
    <div class="mx-3 py-2 d-flex justify-content-between">
      <img class="" src="@/assets/logo-small.svg" alt="" />
      <loader />
    </div>
  </header>
</template>

<script>
import Loader from "./Loader.vue";
export default {
  components: { Loader },
};
</script>

<style lang="scss" scoped LoaderComponent>
@import "@/style/headerBox.scss";
</style>
