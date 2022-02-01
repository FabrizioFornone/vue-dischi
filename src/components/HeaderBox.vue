<template>
  <header>
    <div class="mx-3 py-2 d-flex justify-content-between">
      <div class="d-flex align-item-center">
        <img class="" src="@/assets/logo-small.svg" alt="" />
        <select class="mx-5 px-3" name="" @change="$emit('search', selected)" v-model="selected">
          <option value="all">All</option>
          <option value="rock">Rock</option>
          <option value="pop">Pop</option>
          <option value="jazz">Jazz</option>
          <option value="metal">Metal</option>
        </select>
      </div>
      <loader v-if="loadingValue" />
    </div>
  </header>
</template>

<script>
import Loader from "./Loader.vue";
export default {
  components: { Loader },
  props: {
    discsList: Array,
    loadingValue: Boolean,
  },
  data() {
    return {
      selected: "",
    };
  },
};
</script>

<style lang="scss" scoped LoaderComponent>
@import "@/style/headerBox.scss";
</style>
